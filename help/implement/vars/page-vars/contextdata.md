---
title: contextData
description: Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# contextData

Med kontextdatavariabler kan du definiera anpassade variabler på varje sida som bearbetningsregler kan läsa. I stället för att explicit tilldela värden till Analytics-variabler i koden kan du skicka data i kontextdatavariabler. Bearbetningsregler tar sedan hänsyn till variabelvärden för kontextdata och skickar dem till respektive Analytics-variabler. Se [Bearbeta regler](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) i användarhandboken för Admin.

Kontextdatavariabler är användbara för utvecklingsteam som samlar in data i namngivna element i stället för i numrerade variabler. I stället för att begära att utvecklingsteamen tilldelar sidans författare `eVar10`kan du begära att de tilldelar den `s.contextData["author"]` istället. En Analysadministratör i organisationen kan sedan skapa bearbetningsregler för att mappa kontextdatavariabler till analysvariabler för rapportering. Utvecklingsteamen skulle i slutändan bara bekymra sig om kontextdatavariabler i stället för de många sidvariabler som Adobe erbjuder.

## Sammanhangsdatavariabler i Adobe Experience Platform Launch

Launch har ingen dedikerad plats för att ange kontextdatavariabler. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.contextData i AppMeasurement och Launch, anpassad kodredigerare

Variabeln får inte ett värde direkt `s.contextData` . Ange i stället variabelns egenskaper som en sträng.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Giltiga kontextdatavariabler innehåller endast alfanumeriska tecken, understreck och punkter. Adobe garanterar inte datainsamling i bearbetningsregler om du inkluderar andra tecken, t.ex. bindestreck.
* Starta inte kontextdatavariabler med `"a."`. Det här prefixet är reserverat och används av Adobe. Använd till exempel inte `s.contextData["a.InstallEvent"]`.
* Sammanhangsdatavariabler är inte skiftlägeskänsliga. Variablerna `s.contextData["example"]` och `s.contextData["EXAMPLE"]` är identiska.

## Använd bearbetningsregler för att fylla i analysvariabler

> [!IMPORTANT] Sammanhangsdatavariabler tas bort efter att regler har bearbetats. Om du inte har aktiva bearbetningsregler som placerar värden i variabler, kommer dessa data att gå förlorade permanent!

1. Uppdatera implementeringen för att ange kontextdatavariabelnamn och -värden.
2. Logga in på Adobe Analytics och gå till Admin > Report Suites.
3. Markera önskad rapportserie och gå sedan till Redigera inställningar > Allmänt > Bearbetningsregler.
4. Skapa en bearbetningsregel som ställer in en Analytics-variabel på kontextdatavariabelvärdet.
5. Spara ändringar.

Bearbetningsreglerna börjar gälla omedelbart när de har sparats. De gäller inte historiska data.

## Skicka kontextdata i ett länkspårningsanrop

Inkludera kontextdatavariabeln som en egenskap för `contextData` i `s.linkTrackVars`:

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
