---
description: 'Mätvärden som endast avser det vågräta/lodräta avståndet för data i webbläsarfönstret. Mer specifikt: webbläsaren'
title: Bredd/höjd för webbläsare
topic: Metrics
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bredd/höjd för webbläsare

Mätvärden som endast avser det vågräta/lodräta avståndet för data i webbläsarfönstret. Mer specifikt: webbläsaren

Adobe Analytics använder webbläsarens höjd och bredd endast från första besöket. Resten av träffarna får inte attribueringen för samma besök.
Webbläsarens bredd-/höjdmått fångar liknande men distinkta värden jämfört med [mobilskärmens storlek](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

Om du till exempel bryter ned webbläsarens bredd eller höjd med mobilupplösning måste du vara medveten om följande skillnader:

* Lösningar för mobila enheter är de fysiska värden som är associerade med enheten. Under Lösningar för mobila enheter visas Galaxy S8 till exempel som 2 960 x 1 440. Upplösningen för mobila enheter hämtas från en tredjepartstjänst när enheten har identifierats.
* I stället ser du CSS-värdena (logiska värden) 740 x 360 under värdena för Höjd och Bredd i webbläsaren. Webbläsarvärdena bygger på JavaScript-/CSS-data.
* En kort diskussion finns i [den här tråden](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

