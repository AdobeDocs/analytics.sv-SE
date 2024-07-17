---
title: prop
description: Anpassade variabler som du kan använda i implementeringen.
feature: Variables
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---

# prop

*Den här hjälpsidan beskriver hur du implementerar props. Mer information om hur utkast fungerar som en dimension finns i [prop](/help/components/dimensions/prop.md) i användarhandboken för komponenter.*

Props är anpassade variabler som du kan använda hur du vill. De finns inte kvar efter den träff de har ställts in.

>[!TIP]
>
>Adobe rekommenderar att du använder [eVars](evar.md) i de flesta fall. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de nu uppfyller nästan alla användningsfall för proppar.

Om du har ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) kan du tilldela dessa anpassade dimensioner till värden som är specifika för din organisation. Antalet tillgängliga props beror på ditt kontrakt med Adobe. Upp till 75 props finns om ditt avtal med Adobe stöder det.

## Proppar med Web SDK

Props mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - listproppar anges i en [separat uppsättning fält](#list-props-web-sdk).
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`; eller `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - listutkast ingår i dessa fält.

## Proppar som använder Adobe Analytics-tillägget

Du kan ange props antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på avsnittet [!UICONTROL Props].

Du kan ställa in ett uttryck på ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.prop1 - s.prop75 i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Varje prop-variabel är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras maximala längd är 100 byte. Värden som är längre än 100 byte trunkeras automatiskt när de skickas till Adobe.

```js
s.prop1 = "Example custom value";
```

## Listtecken

Listtecken är en inställning som används för att tillåta variabeln att innehålla flera värden i samma träff. Om den här inställningen inte är aktiverad, eller om fel avgränsare används, behandlas variabeln som ett enskilt värde.

### Konfigurera listproffs

Aktivera listökningar i [Trafikvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) under inställningarna för rapportsviten. Kontrollera att den önskade avgränsaren är korrekt konfigurerad. Adobe har ingen standardavgränsare.

>[!TIP]
>
>Vanliga avgränsare som används i implementeringar är kommatecken (`,`), kolon (`:`), semikolon (`;`) eller rör (`|`). Du kan använda valfri icke-utökad ASCII-avgränsare som passar din implementering bäst.

### Ange listproffs med Web SDK {#list-props-web-sdk}

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) mappas listproppar till `xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`. Web SDK använder automatiskt rätt avgränsare som anges under inställningarna för rapportsviten. Om du anger avgränsaren i XDM-fältet (till exempel `xdm._experience.analytics.customDimensions.props.prop1.delimiter`) åsidosätter det avgränsaren automatiskt från inställningarna för rapportsviten och kan leda till felaktig parsning av listpropsträngen.

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) används samma fält som standarduttryck för AppMeasurementet och  syntax följs.

### Ange visningsinställningar med Adobe Analytics-tillägget och AppMeasurementet

När du har konfigurerat liststeg i rapportsvitens inställningar med den önskade avgränsaren finns det inga andra implementeringsskillnader än att använda avgränsaren.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Listproppar har fortfarande en maxlängd på 100 byte. Det är lättare att nå den här gränsen och trimma eftersom de kan innehålla flera värden. Använd förkortningar eller förkorta värden om du kanske når denna gräns på 100 byte.

Om du anger samma värde mer än en gång i ett listerbjudande tas de bort från rapporteringen. Analysis Workspace räknar antalet träffar där ett värde visas och inte antalet gånger ett värde finns i data.
