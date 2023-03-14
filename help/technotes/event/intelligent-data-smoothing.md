---
title: Intelligent datautjämning
description: Lär dig hur intelligent datautjämning analyserar historiska trender för att förutsäga värdet av mätvärden inom en påverkad tidsperiod.
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
source-git-commit: e0a4caec9bc58a0846cd46871aad3bed99d218a3
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 1%

---

# Intelligent datautjämning

I enstaka fall kan vissa faktorer påverka datakvaliteten. Punkttrafik, implementeringsändringar eller driftavbrott kan påverka integriteten hos insamlade data. De komplicerar också analysen av hur händelsen kan ha påverkat informationens fullständighet.

Intelligent datautjämning är en prototyp i [Analytics Labs](/help/analyze/labs.md) som kan bidra till att slutföra den här vyn genom att analysera historiska trender för att förutsäga värdet av mätvärden inom den berörda tidsperioden. Prototypen använder avancerade maskininlärningsalgoritmer för att kartlägga de förväntade värdena för mätvärden under den tidsperiod som analyseras.

## Kör intelligent datautjämning

1. Gå till Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Starta prototypen Intelligent Data Smoothing.
   ![Starta prototyp](assets/intelligent-ds.png)
1. Lägg till mätvärden som måste analyseras i frihandstabellen. Prototypen fungerar bara med daglig granularitet, så se till att dimensionen i tabellen är Dag.
   ![Lägg till mått](assets/add-metric.png)
1. Välj ett datumintervall som är bredare än händelsens fönster men se till att det innehåller händelsen.
   ![Datumintervall](assets/date-range.png)
1. Klicka på kugghjulsikonen för måttet i frihandstabellen.
   ![Kugghjulsikon](assets/gear-icon.png)
1. Under [!UICONTROL Data Settings]väljer du [!UICONTROL Data smoothing] alternativ.
   ![Datautjämning](assets/column-setting.png)
1. Välj det datum/datumintervall som motsvarar händelsen och klicka på [!UICONTROL Apply].
Se till att dataområdet för Datautjämning är en delmängd av det datumintervall som har valts för panelen. Måtten i tabellen och diagrammet ersätts av de förväntade värdena.
   ![Förväntade värden](assets/predictive-values.png)
