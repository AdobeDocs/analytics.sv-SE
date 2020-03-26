---
description: 'null'
title: Förhandsvisa dimensioner
uuid: dd1f87de-2d83-4c6b-b8cd-ce81c741d7a3
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# Förhandsvisa dimensioner

Håll pekaren över informationsikonen (i) bredvid en dimension. Detta visar de 5 högsta värdena för icke-tidsdimensioner (och 15 för tidsdimensioner). Vi brukade hålla dessa värden statiska (dvs. de 5 valda värdena ändrades aldrig).

![](assets/dimension-preview.png)

Som standard visas nu dynamiska värden i stället för statiska, med möjlighet att omvandla dem till statiska värden. Andra saker att notera:

* När dina data uppdateras uppdateras de dynamiska dimensionskolumnerna så att de aktuella 5/15 dimensionsobjekten visas.
* En kolumn för dynamiska dimensioner som kopieras eller flyttas blir statisk.
* När du hovrar en statisk dimensionskolumn visas en låsikon som anger att dimensionen är statisk.

![](assets/dimension_static.png)

## Visa dimensionsobjekt

När du håller muspekaren över ett mått och klickar på den grå högerpilen bredvid det visas en lista med dimensionsobjekt. Alla listor med dimensionsobjekt visar vanligtvis de översta artiklarna de senaste 30 dagarna.

Om du bläddrar nedåt till listan visas ett **[!UICONTROL Show Top Items From Last 6 Months]**. Klicka på det här alternativet om du vill visa de översta dimensionsobjekten från de senaste 180 dagarna.
