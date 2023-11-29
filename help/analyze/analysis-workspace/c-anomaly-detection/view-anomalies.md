---
description: Du kan visa avvikelser i en tabell eller i ett linjediagram.
title: Visa avvikelser i Analysis Workspace
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# Visa avvikelser i Analysis Workspace

Du kan visa avvikelser i en tabell eller i ett linjediagram.

## Visa avvikelser i en tabell {#section_869A87B92B574A38B017A980ED8A29C5}

Du kan visa avvikelser i en friformstabell i en tidsserie.

1. Markera ikonen för kolumninställningar i kolumnrubriken och kontrollera sedan att [!UICONTROL **Anomalier**] är markerat i listan med alternativ. Mer information finns i [Kolumninställningar](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Klicka utanför inställningsmenyn för att visa den uppdaterade tabellen.

   ![](assets/anomaly_detected.png)

1. Anomalier visas i tabellen enligt följande:

   A **mörkgrå triangel** visas i det övre högra hörnet av varje rad där en dataavvikelse upptäcks.

   Den färgade **lodrät linje** på varje rad anger det förväntade värdet. Den färgade **skuggat område** på varje rad anger det verkliga värdet. Hur raden (förväntat värde) jämförs med det skuggade området (faktiskt värde) avgör om det finns någon avvikelse. (En observation anses vara onormal på grundval av de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används för avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Markera den grå triangeln i det övre högra hörnet av en rad för att visa detaljer om avvikelsen. Detta visar i vilken utsträckning (i procent) det faktiska värdet avviker antingen över eller under det förväntade värdet.

## Visa avvikelser i ett linjediagram {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Linjediagram är den enda visualisering som gör att du kan se avvikelser.

Så här visar du avvikelser i ett linjediagram:

1. Välj inställningsikonen i visualiseringshuvudet och kontrollera sedan att [!UICONTROL **Visa avvikelser**] är markerat i listan med alternativ. Mer information finns i [Linje](/help/analyze/analysis-workspace/visualizations/line.md).

1. (Valfritt) Om du vill att konfidensintervallet ska kunna skalförändra diagrammet väljer du inställningsikonen i visualiseringshuvudet och väljer sedan alternativet **[!UICONTROL Allow anomalies to Scale Y-axis]**.

   Det här alternativet är inte markerat som standard eftersom det ibland kan göra diagrammet mindre läsbart.

1. Klicka utanför inställningsmenyn för att visa det uppdaterade linjediagrammet.

   ![](assets/anomaly_linechart.png)

   Anomalier visas i linjediagrammet enligt följande:

   A **vit punkt** visas på raden där en dataavvikelse upptäcks. (En observation anses vara onormal på grundval av de avancerade statistiska tekniker som beskrivs i [Statistiska tekniker som används för avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **ljusskuggat område** är konfidensintervallet, eller förväntat intervall, där värden ska förekomma. Alla värden som ligger utanför det förväntade intervallet är en avvikelse.

   Om du har flera mätvärden i linjediagrammet visas bara avvikelserna, och du måste hålla muspekaren över varje avvikelse för att se konfidensintervallet för det måttet.

   The **prickad linje** är det exakta förväntade värdet.

1. Klicka på en avvikelse (vit punkt) om du vill visa följande information:

   * Datumet då avvikelsen inträffade

   * avvikelsens råvärde

   * Procentvärdet över eller under det förväntade värdet, som representeras av den helgröna linjen.

   * Länken Analysera för att starta bidragsanalysen

     (Se [Översikt över avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) för mer information.)





