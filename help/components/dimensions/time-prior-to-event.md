---
title: Tid före händelse
description: Hur lång tid det tar mellan mätvärdet och besökets första träff.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Tid före händelse

Dimensionen&quot;Tid före händelse&quot; visar hur lång tid det tog mellan besökets första träff och det önskade måttet. Denna dimension är användbar för att avgöra hur lång tid det tar att träffa på en lyckad händelse, som att skicka formulär eller köpa ett formulär.

## Fyll den här dimensionen med data

Även om den här dimensionen tekniskt sett fungerar som den ska för alla implementeringar fungerar den bäst med anpassade händelser och köphändelser. Adobe rekommenderar att du implementerar anpassade händelser på din webbplats. Om du implementerar anpassade händelser krävs ingen ytterligare implementering för den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena inkluderar tidsbaserade bucklar från `"Less than 1 minute"` till `"More than 15 hours"`. Om det till exempel tog en besökare 23 minuter från den första träffen till ett köp, hör den till under `"10 to 30 minutes"` dimensionsvärdet.
