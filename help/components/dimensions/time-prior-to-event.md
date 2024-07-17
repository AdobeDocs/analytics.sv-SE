---
title: Tid före händelse
description: Hur lång tid det tar mellan mätvärdet och besökets första träff.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---

# Tid före händelse

Tid före händelse [dimension](overview.md) rapporterar hur lång tid som gått mellan besökets första träff och det önskade måttet. Denna dimension är användbar för att avgöra hur lång tid det tar att träffa på en lyckad händelse, som att skicka formulär eller köpa ett formulär.

## Fyll den här dimensionen med data

Även om den här dimensionen tekniskt sett fungerar som den ska för alla implementeringar fungerar den bäst med anpassade händelser och köphändelser. Adobe rekommenderar att du implementerar anpassade händelser på din webbplats. Om du implementerar anpassade händelser krävs ingen ytterligare implementering för den här dimensionen.

## Dimensioner

Dimensioner innehåller tidsbaserade buketter från `"Less than 1 minute"` till `"More than 15 hours"`. Om det till exempel tog en besökare 23 minuter från den första träffen till ett köp, skulle den tillhöra dimensionsobjektet `"10 to 30 minutes"`. Det går inte att anpassa bucklarna för det här måttet.
