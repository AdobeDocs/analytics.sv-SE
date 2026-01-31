---
title: Mappning av dataobjektfält till Adobe Analytics
description: Visa vilka dataobjektfält Experience Platform Edge automatiskt mappar till Analytics-variabler.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Mappning av dataobjektfält till Adobe Analytics

Följande tabell visar dataobjektsfältet som Adobe Experience Platform Edge Network automatiskt mappar till Adobe Analytics. Om du använder dessa sökvägar för dataobjektfält behövs ingen ytterligare konfiguration för att skicka data till Adobe Analytics.

Du bör använda dessa fält om du tänker använda Customer Journey Analytics i framtiden. Med den här implementeringsmetoden kan din organisation skicka data till Adobe med Web SDK utan att följa ett XDM-schema. När din organisation är redo att skicka data till Adobe Experience Platform kan du använda [Datastream-mappning](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep#mapping) för att peka dataobjektfält mot deras respektive XDM-fält.

## Värdeprioriteringar

De flesta dataobjektfält i den här tabellen motsvarar ett [mappat XDM-fält](xdm-var-mapping.md). Vid intag av Adobe Analytics mappas värden först från XDM till analysvariabler. Identifierade dataobjektfält mappas sedan och ersätter tidigare angivna värden när de mappas till samma Analytics-variabel. Om `data.__adobe.analytics.events` till exempel finns, ersätter den hela uppsättningen händelser som annars skulle härledas från XDM. Händelser kombineras inte mellan båda källorna. En tom sträng (`""`) i ett dataobjektfält saknar den mappade analysvariabeln för träffen, även om motsvarande XDM-fält innehåller ett värde.

Vissa dataobjektfält har också stöd för sina respektive [frågeparametervärde](../validate/query-parameters.md) som kortkommandovärden. Du kan använda standardobjektsfält och dataobjektfält i kortskrift på ett utbytbart sätt, förutsatt att de är båda för unika variabler. Undvik att ställa in både ett standardobjektfält och dess respektive dataobjektfält i kortskrift samtidigt. Adobe kan inte garantera vilket fält som prioriteras.

## Mappning av dataobjektfält

Tidigare uppdateringar av den här tabellen finns på den här sidans [implementeringshistorik på GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md). På samma sätt som för AppMeasurement-variabler är alla dataobjektfält skiftlägeskänsliga.

| Sökväg till dataobjektfält | Analysvariabel och beskrivning |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | Dimensionen [Webbläsarhöjd](../../components/dimensions/browser-height.md). Kortkommandofältet `data.__adobe.analytics.bh` stöds också. |
| `data.__adobe.analytics.browserWidth` | Dimensionen [Webbläsarbredd](../../components/dimensions/browser-width.md). Kortkommandofältet `data.__adobe.analytics.bw` stöds också. |
| `data.__adobe.analytics.campaign` | Dimensionen [Spårningskod](../../components/dimensions/tracking-code.md). Kortkommandofältet `data.__adobe.analytics.v0` stöds också. |
| `data.__adobe.analytics.channel` | Dimensionen för [webbplatsavsnittet](../../components/dimensions/site-section.md). Kortkommandofältet `data.__adobe.analytics.ch` stöds också. |
| `data.__adobe.analytics.colorDepth` | Dimensionen [Färgdjup](../../components/dimensions/color-depth.md). Kortkommandofältet `data.__adobe.analytics.c` stöds också. |
| `data.__adobe.analytics.connectionType` | Dimensionen [Anslutningstyp](../../components/dimensions/connection-type.md). Kortkommandofältet `data.__adobe.analytics.ct` stöds också. |
| `data.__adobe.analytics.contextData` | [Kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | Dimensionen [Cookie stöder](../../components/dimensions/cookie-support.md). Kortkommandofältet `data.__adobe.analytics.k` stöds också. |
| `data.__adobe.analytics.currencyCode` | Implementeringsvariabeln [`currencyCode`](../vars/config-vars/currencycode.md). Kortkommandofältet `data.__adobe.analytics.cc` stöds också. |
| `data.__adobe.analytics.dynamicVariablePrefix` | Implementeringsvariabeln [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md)-dimensioner. Kortkommandofälten `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` stöds också. |
| `data.__adobe.analytics.events` | [Anpassade händelser](../../components/metrics/custom-events.md). Formatera det här fältet ungefär som implementeringsvariabeln [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | Dimensionen [Java aktiverad](../../components/dimensions/java-enabled.md). Kortkommandofältet `data.__adobe.analytics.v` stöds också. |
| `data.__adobe.analytics.latitude` | Hjälper dig att ange dimensionerna för den mobila livscykeln [Plats](../../components/dimensions/lifecycle-dimensions.md). Kortkommandofältet `data.__adobe.analytics.lat` stöds också. |
| `data.__adobe.analytics.linkName` | Dimensionen [Egen länk](../../components/dimensions/custom-link.md), [Hämta länk](../../components/dimensions/download-link.md) eller [Avsluta länk](../../components/dimensions/exit-link.md), beroende på värdet i `data.__adobe.analytics.linkType`. Kortkommandofältet `data.__adobe.analytics.pev2` stöds också. |
| `data.__adobe.analytics.linkURL` | Implementeringsvariabeln [`linkURL`](../vars/config-vars/linkurl.md). Kortkommandofältet `data.__adobe.analytics.pev1` stöds också. |
| `data.__adobe.analytics.linkType` | Anger vilken typ av länk som klickas. Giltiga värden är `o` (anpassade länkar), `d` (hämtningslänkar) och `e` (avsluta länkar). Kortkommandofältet `data.__adobe.analytics.pe` stöds också. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) implementeringsvariabler. Kortkommandofälten `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` stöds också. |
| `data.__adobe.analytics.longitude` | Hjälp med att ange dimensionerna för den mobila livscykeln [Plats](../../components/dimensions/lifecycle-dimensions.md). Kortkommandofältet `data.__adobe.analytics.lon` stöds också. |
| `data.__adobe.analytics.pageName` | Dimensionen [Sida](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | Dimensionen för [sid-URL](/help/components/dimensions/page-url.md). Kortkommandofältet `data.__adobe.analytics.g` stöds också. |
| `data.__adobe.analytics.pageType` | Implementeringsvariabeln [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md)-dimensioner. Kortkommandofälten `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` stöds också. |
| `data.__adobe.analytics.purchaseID` | Implementeringsvariabeln [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | Implementeringsvariabeln [`products`](../vars/page-vars/products.md), med liknande formatering. |
| `data.__adobe.analytics.referrer` | Dimensionen [Referent](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | Dimensionen [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md). Kortkommandofältet `data.__adobe.analytics.s` stöds också. |
| `data.__adobe.analytics.server` | Dimensionen [Server](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | Implementeringsvariabeln [`transactionID`](../vars/page-vars/transactionid.md). Kortkommandofältet `data.__adobe.analytics.xact` stöds också. |
| `data.__adobe.analytics.zip` | Dimensionen [Postnummer](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
