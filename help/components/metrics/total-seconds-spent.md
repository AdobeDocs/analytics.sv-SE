---
title: Totalt antal sekunder som använts
description: Det sammanlagda antalet sekunder som har ägnats åt dimensionsobjektet.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# Totalt antal sekunder som använts

Antal sekunder som har använts [mått](overview.md) visar det sammanlagda antalet sekunder en besökare har tillbringat på ett visst dimensionsobjekt. Det här måttet är användbart när du vill ha obegränsad tid på ett visst dimensionsobjekt och inte medelvärden som annan tidsåtgång för mätvärden.

I Report Builder heter det här måttet&quot;Total tid tillbringad&quot;.

## Hur det här måttet beräknas

Det här måttet använder följande steg för att mäta beräkning:

1. Titta på tidsstämpeln för en viss träff.
2. Jämför träffen med tidsstämpeln för nästa träff i besöket. Både sidvy och länkspårning träffar.
3. Antalet sekunder som förflutit mellan de två träffarna bidrar till dimensionsobjektet.

Beständiga variabler, till exempel [eVars](../dimensions/evar.md), räkna till totalt antal sekunder som har använts. Trafikvariabler, t.ex. [proppar](../dimensions/prop.md), tar med sekunder som använts för efterföljande länkspårningsanrop.

>[!TIP]
>
>Tid som använts mäts inte för den senaste besöksträffen eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid. Detta koncept gäller också besök som består av en enda träff (ett studs).

Se [Tidsåtgång - översikt](time-spent.md) om du vill ha mer allmän information om hur länge du har tillbringat.
