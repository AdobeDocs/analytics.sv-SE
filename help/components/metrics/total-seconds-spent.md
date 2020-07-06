---
title: Totalt antal sekunder som använts
description: Det sammanlagda antalet sekunder som har ägnats åt dimensionsvärdet.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# Totalt antal sekunder som använts

Mätvärdet för Totalt antal sekunder som har använts visar det sammanlagda antalet sekunder en besökare har tillbringat med ett givet dimensionsvärde. Det här måttet är användbart när du vill ha obegränsad tid på ett givet dimensionsvärde och inte medelvärden som annan tidsåtgång för mätvärden.

I Report Builder heter det här måttet&quot;Total tid spenderad&quot;.

## Hur det här måttet beräknas

Det här måttet använder följande steg för att mäta beräkning:

1. Titta på tidsstämpeln för en viss träff.
2. Jämför träffen med tidsstämpeln för nästa träff i besöket. Både sidvy och länkspårning träffar.
3. Antalet sekunder som förflutit mellan de två träffarna bidrar till dimensionsvärdet.

Beständiga variabler, till exempel [eVars](../dimensions/evar.md), räknas mot det totala antalet sekunder som används. Trafikvariabler, till exempel [props](../dimensions/prop.md), inkluderar sekunder som har använts för efterföljande länkspårningsanrop.

>[!TIP]
>
>Tid som använts mäts inte för den senaste besöksträffen eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid. Detta koncept gäller också besök som består av en enda träff (ett studs).

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](time-spent.md) .
