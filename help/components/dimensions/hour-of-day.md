---
title: Timme på dagen
description: Dagens numeriska timme, oavsett vilken dag.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Timme på dagen

Dimensionen &quot;Timme på dagen&quot; rapporterar den numeriska timmen för en given dag som en dimensionspost. Om du till exempel har en rapport som sträcker sig från 1 januari till 7 grupperas den första timmen för varje dag till samma dimensionsobjekt. Den här rapporten är värdefull om du vill att en rapport ska delas upp efter relativ tid på dagen, men inte vill ha en statisk timme som dimensionsobjekt. Det är särskilt värdefullt som en dimension i schemalagda rapporter, eftersom den här dimensionen följer det valda datumintervallet.

Denna dimension baseras på rapportsvitens tidszon, och inte på besökarens lokala tidszon. Om din rapportsvit till exempel är i Berg och en besökare i Kalifornien besöker din webbplats kl. 10.00 PST-tid, kommer träffgrupperna under `11:00 AM` dimensionsposten. Om du vill ha en dimension som registrerar den lokala besökarens tid bör du använda plugin-programmet [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten är `12:00 AM` - `11:00 PM`, som representerar timmen på dagen då träffen inträffade (avrundad nedåt). Om till exempel en träff genererades klockan 17:58 grupperas den under dimensionsobjektet för `3:00 PM`.
