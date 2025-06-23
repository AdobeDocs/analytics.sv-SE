---
title: contextData
description: Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa.
feature: Appmeasurement Implementation
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# contextData

Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa. I stället för att explicit tilldela värden till Analytics-variabler i koden kan du skicka data i kontextdatavariabler. Bearbetningsregler tar sedan hänsyn till variabelvärden för kontextdata och skickar dem till respektive Analytics-variabler. Se [Bearbetar regler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) i användarhandboken för Admin.

Kontextdatavariabler är användbara för utvecklingsteam som samlar in data i namngivna element i stället för i numrerade variabler. I stället för att begära utvecklarteam tilldelar du till exempel sidans författare till `eVar10`, kan du begära att de tilldelar den till `s.contextData["author"]` i stället. En Analysadministratör i organisationen kan sedan skapa bearbetningsregler för att mappa kontextdatavariabler till analysvariabler för rapportering. Utvecklingsteamen skulle i slutändan bara bekymra sig om kontextdatavariabler i stället för de många sidvariabler som Adobe erbjuder.

## Sammanhangsdatavariabler med Web SDK

Om du använder [**XDM-objektet**](/help/implement/aep-edge/xdm-var-mapping.md) inkluderas automatiskt alla fält som inte mappar till en Adobe Analytics-variabel som kontextdatavariabel. Du kan också ange kontextdata explicit med XDM-objektet. Du kan sedan använda [Bearbetningsregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) för att tilldela kontextdatavariabeln till den önskade Analytics-variabeln.  Mer information finns i [Mappa andra XDM-fält till analysvariabler](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

Om du använder [**dataobjektet**](/help/implement/aep-edge/data-var-mapping.md) finns alla kontextdatavariabler i `data.__adobe.analytics.contextData` som nyckelvärdepar:

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

Gränssnittet [Bearbetningsregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) skulle visa `example_variable` och `second_example` i tillämpliga nedrullningsbara menyer.

## Sammanhangsdatavariabler med Adobe Analytics-tillägget

Adobe Experience Platform Data Collection har ingen dedikerad plats för att ange kontextdatavariabler. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.contextData i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.contextData` får inget värde direkt. Ställ i stället in variabelns egenskaper på en sträng.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Giltiga kontextdatavariabler innehåller endast alfanumeriska tecken, understreck och punkter. Adobe garanterar inte datainsamling i bearbetningsregler om du inkluderar andra tecken, t.ex. bindestreck.
* Starta inte kontextdatavariabler med `"a."`. Prefixet är reserverat och används av Adobe. Använd till exempel inte `s.contextData["a.InstallEvent"]`.
* Sammanhangsdatavariabler är inte skiftlägeskänsliga. Variablerna `s.contextData["example"]` och `s.contextData["EXAMPLE"]` är identiska.
* En enskild nyckel får inte innehålla mer än ett värde. Om du vill använda kontextdatavariabler för flervärdesvariabler sammanfogar du alla värden med en avgränsare (vanligtvis ett komma) och skickar dem antingen till en [listprop](prop.md#list-props) eller en [listvariabel](list.md) med bearbetningsregler.

## Använd bearbetningsregler för att fylla i analysvariabler

>[!WARNING]
>
>Sammanhangsdatavariabler tas bort efter att regler har bearbetats. Om du inte har aktiva bearbetningsregler som placerar värden i variabler, kommer dessa data att gå förlorade permanent!

1. Uppdatera implementeringen för att ange kontextdatavariabelnamn och -värden.
2. Logga in på Adobe Analytics och gå till **[!UICONTROL Admin]** > **[!UICONTROL Report]** sviter.
3. Välj önskad rapportsvit och gå sedan till **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
4. Skapa en bearbetningsregel som ställer in en Analytics-variabel på kontextdatavariabelvärdet.
5. Spara ändringar.

Bearbetningsreglerna börjar gälla omedelbart när de har sparats. De gäller inte historiska data.

## Skicka kontextdata i ett länkspårningsanrop

Inkludera kontextdatavariabeln som en egenskap för `contextData` i [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Öka händelser med hjälp av kontextdatavariabler

När du skapar bearbetningsregler kan du tilldela kontextdatavariabler till händelser.

* Om en kontextdatavariabel innehåller någon typ av text ökas händelsen med ett.
* Om en kontextdatavariabel innehåller ett heltal ökas händelsen med det heltalsvärdet.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
