---
description: Visa de översta värdena för en dimension innan du använder den i ett projekt.
title: Förhandsvisa dimensioner
uuid: dd1f87de-2d83-4c6b-b8cd-ce81c741d7a3
feature: Grundläggande om arbetsytan
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---


# Förhandsvisa dimensioner

Håll pekaren över informationsikonen (i) bredvid en dimension. Detta visar de 5 högsta värdena för icke-tidsdimensioner (och 15 för tidsdimensioner). Vi brukade hålla dessa värden statiska (dvs. de 5 valda värdena ändrades aldrig).

![](assets/dimension-preview.png)

Som standard visas nu dynamiska värden i stället för statiska, med möjlighet att omvandla dem till statiska värden. Andra saker att notera:

* När data uppdateras uppdateras kolumnerna för dynamiska mått så att de aktuella 5/15 måttobjekten visas.
* En kolumn för dynamiska mått som kopieras eller flyttas blir statisk.
* När du håller markören över en statisk måttkolumn visas en låsikon, som anger att måttet är statiskt.

![](assets/dimension_static.png)

## Visa dimensionsobjekt

När du håller muspekaren över ett mått och klickar på den grå högerpilen bredvid det visas en lista med dimensionsobjekt. Alla listor med dimensionsobjekt visar vanligtvis de översta artiklarna de senaste 30 dagarna.

Om du bläddrar nedåt i listan visas ett **[!UICONTROL Show Top Items From Last 6 Months]**. Klicka på det här alternativet om du vill visa de översta dimensionsobjekten från de senaste 180 dagarna.
