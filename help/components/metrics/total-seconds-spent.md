---
title: Totalt antal sekunder som använts
description: Det sammanlagda antalet sekunder som har ägnats åt dimensionsobjektet.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# Totalt antal sekunder som använts

Mätvärdet för Totalt antal sekunder som använts visar det sammanlagda antalet sekunder som en besökare har tillbringat på ett visst dimensionsobjekt. Det här måttet är användbart när du vill ha obegränsad tid på ett visst dimensionsobjekt och inte medelvärden som annan tidsåtgång för mätvärden.

I Report Builder heter det här måttet&quot;Total tid spenderad&quot;.

## Hur det här måttet beräknas

Det här måttet använder följande steg för att mäta beräkning:

1. Titta på tidsstämpeln för en viss träff.
2. Jämför träffen med tidsstämpeln för nästa träff i besöket. Både sidvy och länkspårning träffar.
3. Antalet sekunder som förflutit mellan de två träffarna bidrar till dimensionsobjektet.

Beständiga variabler, till exempel [eVars](../dimensions/evar.md), räknas mot det totala antalet sekunder som används. Trafikvariabler, till exempel [props](../dimensions/prop.md), inkluderar sekunder som har använts för efterföljande länkspårningsanrop.

>[!TIP]
>
>Tid som använts mäts inte för den senaste besöksträffen eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid. Detta koncept gäller också besök som består av en enda träff (ett studs).

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md) .
