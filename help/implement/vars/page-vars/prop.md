---
title: egenskap
description: Anpassade variabler som du kan använda i implementeringen.
feature: Variables
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# egenskap

*På den här hjälpsidan beskrivs hur du implementerar props. Mer information om hur utkast fungerar som en dimension finns i [prop](/help/components/dimensions/prop.md) i användarhandboken för komponenter.*

Props är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in.

>[!TIP]
>
>Adobe rekommenderar att du använder [eVars](evar.md) i de flesta fall. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de fyller i nästan alla användningsområden för proppar.

Om du har en [konstruktionsdokument](/help/implement/prepare/solution-design.md)kan du tilldela dessa anpassade dimensioner till värden som är specifika för din organisation. Antalet tillgängliga props beror på ditt kontrakt med Adobe. Upp till 75 props finns om ditt avtal med Adobe stöder det.

## Proppar med Web SDK

Profiler är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fälten `_experience.analytics.customDimensions.props.prop1` till `_experience.analytics.customDimensions.props.prop75`.

## Proppar som använder Adobe Analytics-tillägget

Du kan ange props antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL Props] -avsnitt.

Du kan ställa in ett uttryck på ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.prop1 - s.prop75 in AppMeasurement and the Analytics extension custom code editor

Varje prop-variabel är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras maximala längd är 100 byte. värden som är längre än 100 byte trunkeras automatiskt när de skickas till Adobe.

```js
s.prop1 = "Example custom value";
```

## Visa utkast

Listtecken är en inställning som används för att tillåta variabeln att innehålla flera värden i samma träff. Om den här inställningen inte är aktiverad, eller om fel avgränsare används, behandlas variabeln som ett enskilt värde.

### Konfigurera listproffs

Aktivera listtips i inställningarna för rapportsviten. Se [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i användarhandboken för Admin. Kontrollera att den önskade avgränsaren är korrekt konfigurerad. Adobe har ingen standardavgränsare.

>[!TIP]
>
>Vanliga avgränsare som används i implementeringar är kommatecken (`,`), kolon (`:`), semikolon (`;`), eller rör (`|`). Du kan använda valfri avgränsare som passar din implementering bäst.

### Ange listans förtecken

När du har konfigurerat liststeg i rapportsvitens inställningar med den önskade avgränsaren finns det inga andra implementeringsskillnader än att använda avgränsaren.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Listproppar har fortfarande en maxlängd på 100 byte. Det är lättare att nå den här gränsen och trimma eftersom de kan innehålla flera värden. Använd förkortningar eller förkorta värden om du kanske når denna gräns på 100 byte.

Om du anger samma värde mer än en gång i ett listerbjudande tas de bort från rapporteringen. Analysis Workspace räknar antalet träffar där ett värde visas och inte antalet gånger ett värde finns i data.
