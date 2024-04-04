---
title: Variabelmappning för dataobjekt till Adobe Analytics
description: Visa vilka dataobjektfält Experience Platform Edge automatiskt mappar till analysvariabler.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 3a530e3e47ac9d6cf2b711cecd07f2c33765d63c
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 0%

---

# Variabelmappning för dataobjekt till Adobe Analytics

Följande tabell visar de dataobjektsvariabler som Adobe Experience Platform Edge Network automatiskt mappar till Adobe Analytics. Om du använder dessa sökvägar för dataobjektfält behövs ingen ytterligare konfiguration för att skicka data till Adobe Analytics.

Du bör använda dessa fält om du tänker använda Customer Journey Analytics i framtiden. Med den här implementeringsmetoden kan din organisation skicka data till Adobe med Web SDK utan att följa ett XDM-schema. När ni är redo att skicka data till Adobe Experience Platform kan ni använda [Datastream-mappning](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) för att peka dataobjektfält mot deras respektive XDM-fält.

## Värdeprioriteringar

De flesta dataobjektfält i den här tabellen sammanfaller med en [mappat XDM-fält](xdm-var-mapping.md). Om du anger båda `data` objektfält och dess respektive XDM-fält, dataobjektfältet har prioritet. Om du använder både XDM-objektfältet och dataobjektfältet rekommenderar Adobe att du ställer in anpassade händelser med dataobjektfältet. Om fältet `data.__adobe.analytics.events` skriver den över alla XDM-objektfält som är relaterade till handel och anpassade händelser.

Vissa dataobjektfält stöder också deras respektive fält [Frågeparametervärde](../validate/query-parameters.md) som kortskriftsvärden. Du kan använda standardobjektsfält och dataobjektfält i kortskrift på ett utbytbart sätt, förutsatt att de är båda för unika variabler. Undvik att ställa in både ett standardobjektfält och dess respektive dataobjektfält i kortskrift samtidigt. Adobe kan inte garantera vilket fält som prioriteras.

## Mappning av dataobjektfält

Tidigare uppdateringar av tabellen finns på den här sidans [implementeringshistorik på GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md).

| Sökväg till dataobjektfält | Analysvariabel och beskrivning |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | The [Webbläsarhöjd](../../components/dimensions/browser-height.md) dimension. Kortkommandofältet `data.__adobe.analytics.bh` stöds också. |
| `data.__adobe.analytics.browserWidth` | The [Bredd på webbläsare](../../components/dimensions/browser-width.md) dimension. Kortkommandofältet `data.__adobe.analytics.bw` stöds också. |
| `data.__adobe.analytics.campaign` | The [Spårningskod](../../components/dimensions/tracking-code.md) dimension. Kortkommandofältet `data.__adobe.analytics.v0` stöds också. |
| `data.__adobe.analytics.channel` | The [Site section](../../components/dimensions/site-section.md) dimension. Kortkommandofältet `data.__adobe.analytics.ch` stöds också. |
| `data.__adobe.analytics.colorDepth` | The [Färgdjup](../../components/dimensions/color-depth.md) dimension. Kortkommandofältet `data.__adobe.analytics.c` stöds också. |
| `data.__adobe.analytics.connectionType` | The [Anslutningstyp](../../components/dimensions/connection-type.md) dimension. Kortkommandofältet `data.__adobe.analytics.ct` stöds också. |
| `data.__adobe.analytics.contextData` | [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | The [Cookie-stöd](../../components/dimensions/cookie-support.md) dimension. Kortkommandofältet `data.__adobe.analytics.k` stöds också. |
| `data.__adobe.analytics.currencyCode` | The [`currencyCode`](../vars/config-vars/currencycode.md) implementeringsvariabel. Kortkommandofältet `data.__adobe.analytics.cc` stöds också. |
| `data.__adobe.analytics.dynamicVariablePrefix` | The [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) implementeringsvariabel. |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensioner. Kortkommandofält `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` stöds också. |
| `data.__adobe.analytics.events` | [Anpassade händelser](../../components/metrics/custom-events.md). Formatera det här fältet på samma sätt som [`events`](../vars/page-vars/events/events-overview.md) implementeringsvariabel. |
| `data.__adobe.analytics.javaEnabled` | The [Java aktiverat](../../components/dimensions/java-enabled.md) dimension. Kortkommandofältet `data.__adobe.analytics.v` stöds också. |
| `data.__adobe.analytics.latitude` | Hjälper dig att ange [Plats](../../components/dimensions/lifecycle-dimensions.md) mobila livscykeldimensioner. Kortkommandofältet `data.__adobe.analytics.lat` stöds också. |
| `data.__adobe.analytics.linkName` | The [Egen länk](../../components/dimensions/custom-link.md), [Hämta länk](../../components/dimensions/download-link.md), eller [Avsluta länk](../../components/dimensions/exit-link.md) dimension, beroende på värdet i `data.__adobe.analytics.linkType`. Kortkommandofältet `data.__adobe.analytics.pev2` stöds också. |
| `data.__adobe.analytics.linkURL` | The [`linkURL`](../vars/config-vars/linkurl.md) implementeringsvariabel. Kortkommandofältet `data.__adobe.analytics.pev1` stöds också. |
| `data.__adobe.analytics.linkType` | Anger vilken typ av länk som klickas. Giltiga värden är `o` (Anpassade länkar), `d` (Hämta länkar) och `e` (Avsluta länkar). Kortkommandofältet `data.__adobe.analytics.pe` stöds också. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) implementeringsvariabler. Kortkommandofält `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` stöds också. |
| `data.__adobe.analytics.longitude` | Hjälp med att ställa in [Plats](../../components/dimensions/lifecycle-dimensions.md) mobila livscykeldimensioner. Kortkommandofältet `data.__adobe.analytics.lon` stöds också. |
| `data.__adobe.analytics.pageName` | The [Sida](/help/components/dimensions/page.md) dimension. |
| `data.__adobe.analytics.pageURL` | The [Sidans URL](/help/components/dimensions/page-url.md) dimension. Kortkommandofältet `data.__adobe.analytics.g` stöds också. |
| `data.__adobe.analytics.pageType` | The [`pageType`](../vars/page-vars/pagetype.md) implementeringsvariabel. |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensioner. Kortkommandofält `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` stöds också. |
| `data.__adobe.analytics.purchaseID` | The [`purchaseID`](../vars/page-vars/purchaseid.md) implementeringsvariabel. |
| `data.__adobe.analytics.products` | The [`products`](../vars/page-vars/products.md) implementeringsvariabel, med liknande formatering. |
| `data.__adobe.analytics.referrer` | The [Referent](/help/components/dimensions/referrer.md) dimension. |
| `data.__adobe.analytics.resolution` | The [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md) dimension. Kortkommandofältet `data.__adobe.analytics.s` stöds också. |
| `data.__adobe.analytics.server` | The [Server](/help/components/dimensions/server.md) dimension. |
| `data.__adobe.analytics.tnta` | Används i A4T-integreringar. |
| `data.__adobe.analytics.transactionID` | The [`transactionID`](../vars/page-vars/transactionid.md) implementeringsvariabel. Kortkommandofältet `data.__adobe.analytics.xact` stöds också. |
| `data.__adobe.analytics.zip` | The [Postnummer](../../components/dimensions/zip-code.md) dimension. |

{style="table-layout:auto"}
