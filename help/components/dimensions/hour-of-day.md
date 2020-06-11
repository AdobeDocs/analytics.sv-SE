---
title: Timme på dagen
description: Dagens numeriska timme, oavsett vilken dag.
translation-type: tm+mt
source-git-commit: 226c54b782651ea8c6f4b7bb8030a1513c440a1d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Timme på dagen

Dimensionen Timme på dagen rapporterar den numeriska timmen för en given dag som ett dimensionsvärde. Om du till exempel har en rapport som sträcker sig från 1 januari till 7 grupperas den första timmen för varje dag till samma dimensionsvärde. Den här rapporten är värdefull om du vill att en rapport ska delas upp efter relativ tid på dagen, men inte vill att en statisk timme ska vara dimensionsvärden. Det är särskilt värdefullt som en dimension i schemalagda rapporter, eftersom den här dimensionen följer det valda datumintervallet.

Denna dimension baseras på rapportsvitens tidszon, och inte på besökarens lokala tidszon. Om din rapportsvit till exempel är i Mountain och en besökare i Kalifornien besöker din webbplats kl. 10.00 PST-tid, så är det träffgrupperna under `11:00 AM` dimensionsvärdet. Om du vill ha en dimension som registrerar den lokala besökarens tid bör du använda plugin-programmet [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena är `12:00 AM` - `11:00 PM`som representerar timmen på dagen då träffen inträffade (avrundad nedåt). Om en träff till exempel genererades klockan 17:58 grupperas den under dimensionsvärdet `3:00 PM`.
