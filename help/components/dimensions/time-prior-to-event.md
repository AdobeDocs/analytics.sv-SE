---
title: Tid före händelse
description: Hur lång tid det tar mellan mätvärdet och besökets första träff.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Tid före händelse

Dimensionen&quot;Tid före händelse&quot; visar hur lång tid det tog mellan besökets första träff och det önskade måttet. Denna dimension är användbar för att avgöra hur lång tid det tar att träffa på en lyckad händelse, som att skicka formulär eller köpa ett formulär.

## Fyll den här dimensionen med data

Även om den här dimensionen tekniskt sett fungerar som den ska för alla implementeringar fungerar den bäst med anpassade händelser och köphändelser. Adobe rekommenderar att du implementerar anpassade händelser på din webbplats. Om du implementerar anpassade händelser krävs ingen ytterligare implementering för den här dimensionen.

## Dimensioner

Dimensioner kan vara tidsbaserade buketter från `"Less than 1 minute"` till `"More than 15 hours"`. Om det t.ex. tog en besökare 23 minuter från den första träffen till ett köp, hör den till `"10 to 30 minutes"` dimensionsobjekt. Det går inte att anpassa bucklarna för det här måttet.
