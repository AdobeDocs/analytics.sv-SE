---
title: contextData
description: Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# contextData

Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa. I stället för att explicit tilldela värden till Analytics-variabler i koden kan du skicka data i kontextdatavariabler. Bearbetningsregler tar sedan hänsyn till variabelvärden för kontextdata och skickar dem till respektive Analytics-variabler. Se [Bearbetar regler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) i användarhandboken för Admin.

Kontextdatavariabler är användbara för utvecklingsteam som samlar in data i namngivna element i stället för i numrerade variabler. I stället för att begära utvecklarteam tilldelar du till exempel sidans författare `eVar10`kan du begära att de tilldelar den till `s.contextData["author"]` i stället. En Analysadministratör i organisationen kan sedan skapa bearbetningsregler för att mappa kontextdatavariabler till analysvariabler för rapportering. Utvecklingsteamen skulle i slutänden bara bekymra sig om kontextdatavariabler i stället för de många sidvariablerna som Adobe erbjuder.

## Sammanhangsdatavariabler som använder taggar i Adobe Experience Platform

Användargränssnittet för datainsamling har ingen dedikerad plats för att ange kontextdatavariabler. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.contextData i AppMeasurement och anpassad kodredigerare

The `s.contextData` variabeln får inte ett värde direkt. Ange i stället variabelns egenskaper som en sträng.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Giltiga kontextdatavariabler innehåller endast alfanumeriska tecken, understreck och punkter. Adobe garanterar inte datainsamling i bearbetningsregler om du inkluderar andra tecken, t.ex. bindestreck.
* Starta inte kontextdatavariabler med `"a."`. Det här prefixet är reserverat och används av Adobe. Använd till exempel inte `s.contextData["a.InstallEvent"]`.
* Sammanhangsdatavariabler är inte skiftlägeskänsliga. Variablerna `s.contextData["example"]` och `s.contextData["EXAMPLE"]` är identiska.

## Använd bearbetningsregler för att fylla i analysvariabler

>[!WARNING]
>
>Sammanhangsdatavariabler tas bort efter att regler har bearbetats. Om du inte har aktiva bearbetningsregler som placerar värden i variabler, kommer dessa data att gå förlorade permanent!

1. Uppdatera implementeringen för att ange kontextdatavariabelnamn och -värden.
2. Logga in på Adobe Analytics och gå till Admin > Report Suites.
3. Markera önskad rapportserie och gå sedan till Redigera inställningar > Allmänt > Bearbetningsregler.
4. Skapa en bearbetningsregel som ställer in en Analytics-variabel på kontextdatavariabelvärdet.
5. Spara ändringar.

Bearbetningsreglerna börjar gälla omedelbart när de har sparats. De gäller inte historiska data.

## Skicka kontextdata i ett länkspårningsanrop

Inkludera kontextdatavariabeln som en egenskap för `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

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
