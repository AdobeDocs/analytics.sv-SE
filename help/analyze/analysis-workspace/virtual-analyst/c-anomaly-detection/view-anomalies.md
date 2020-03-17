---
description: Du kan visa avvikelser i en tabell eller i ett linjediagram.
title: Visa avvikelser i analysarbetsytan
uuid: 270a7ea9-6485-4c83-8220-5a2200bd7200
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visa avvikelser i analysarbetsytan

Du kan visa avvikelser i en tabell eller i ett linjediagram.

## Visa avvikelser i en tabell {#section_869A87B92B574A38B017A980ED8A29C5}

I en friformstabell i en tidsserie flaggas nu varje rad automatiskt med ett mörkgrått utropstecken om en dataavvikelse har upptäckts.

![](assets/anomaly_detected.png)

Den lodräta grå linjen i varje rad anger det förväntade värdet. När du håller pekaren över utropstecknet anges i vilken utsträckning avvikelsen avviker från det förväntade värdet (i + eller - %).

## Visa avvikelser i ett linjediagram {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Linjediagrammet visar det ljusgröna konfidensbandet med avvikande värden (vita punkter).

Om du klickar på en vit punkt blir den grön och den visar dig:

* Datumet då avvikelsen inträffade
* avvikelsens råvärde
* Procentvärdet över eller under det förväntade värdet, som representeras av den helgröna linjen.
* Länken Analysera för att starta [bidragsanalys](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).

![](assets/anomaly_linechart.png)

Om du har flera mätvärden i linjediagrammet visar vi bara avvikelserna och du måste hovra över varje avvikelse för att se konfidensintervallet för det måttet.

Konfidensintervallet för avvikelseidentifiering skalar inte automatiskt y-axeln i en visualisering för att göra diagrammet mer läsbart.

Du kan välja att tillåta konfidensintervallet för att skala diagrammet. Klicka bara på ikonen Inställningar (kugghjulet) och markera **[!UICONTROL Allow Anomaly Detection to Scale Y Axis]**.

![](assets/scale-y-axis.png)

