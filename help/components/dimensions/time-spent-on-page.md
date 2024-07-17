---
title: Tid som använts på sidan
description: Den tid en besökare tillbringade på sidan.
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# Tid som använts på sidan

Den tid som har använts på sidan [dimension](overview.md) registrerar hur lång tid en besökare har tillbringat på sidan. Följande steg används för att mäta beräkningen:

1. Titta på tidsstämpeln för en viss träff.
2. Jämför träffen med tidsstämpeln för nästa träff i besöket. Både sidvy och länkspårning träffar.
3. Den tid som förflutit mellan dessa två träffar bidrar till den tid som tillbringas.

Den här dimensionen är värdefull när du vill förstå hur länge besökarna interagerar med ett givet mätvärde på webbplatsen.

>[!TIP]
>
>Tid som använts mäts inte för den senaste besöksträffen eftersom det inte finns någon efterföljande bildbegäran för att mäta förfluten tid. Detta koncept gäller också besök som består av en enda träff (ett studs).

Den här dimensionen är träffbaserad, vilket innebär att värdet är olika för varje träff. Jämför den här dimensionen med [Tid per besök](time-spent-per-visit.md), som är en besöksbaserad dimension. Högre tidsåtgång innebär att en besökare stannar längre på en sida (träff).

![Tid som använts på sidan](../metrics/assets/time-spent2.png)

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Det finns flera dimensioner för tidsåtgången på sidan:

* **Tid som har använts på sidan - paketerad**: Den tid som har använts är spärrad. Dimensionens objekt varierar från `"Less than 15 seconds"` till `"More than 30 minutes"`. Tiden mellan träffar varar normalt inte längre än 30 minuter, men tiden mellan träffarna kan överstiga 30 minuter om tidsstämplade träffar eller datakällor används.
* **Tid som har använts på sidan - granulärt**: Varje antal sekunder är ett unikt dimensionsobjekt.

Mer allmän information om hur lång tid du tillbringar finns i [Tidsåtgång - översikt](../metrics/time-spent.md).
