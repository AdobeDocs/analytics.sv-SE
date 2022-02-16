---
description: Visa de översta värdena för en dimension innan du använder den i ett projekt.
title: Förhandsvisa dimensioner
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 29%

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

Om du bläddrar nedåt till listan visas en **[!UICONTROL Show Top Items From Last 6 Months]**. Klicka på det här alternativet om du vill visa de översta dimensionsobjekten från de senaste 180 dagarna.
