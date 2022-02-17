---
title: Sökningar
description: Antal gånger en träff matchade externa sökvillkor.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---

# Sökningar

Måttet Sökningar visar antalet träffar som matchar Adobe externa sökidentifiering. Det här måttet är användbart när du vill titta på dimensionsobjekt som inte är sökningar och se hur de bidrog till sökmotortrafiken.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar Adobe externa sökdetektering. Den måste överensstämma med båda följande:

* träffens referensvärde är en sökdomän som Adobe känner igen
* Den refererande URL:en för träffen innehåller en nyckelordsfrågesträngsparameter. På grund av modern sekretesspraxis är det här frågesträngsvärdet vanligtvis tomt. Adobe känner igen tomma nyckelordsfrågesträngar som en del av sökningsidentifieringen.
