---
title: Sökningar
description: Antal gånger en träff matchade externa sökvillkor.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---


# Sökningar

Måttet Sökningar visar antalet träffar som matchar Adobes externa sökidentifiering. Det här måttet är användbart när du vill titta på dimensionsobjekt som inte är sökningar och se hur de bidrog till sökmotortrafiken.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar Adobes externa sökidentifiering. Den måste överensstämma med båda följande:

* träffens referensvärde är en sökdomän som känns igen av Adobe
* Den refererande URL:en för träffen innehåller en nyckelordsfrågesträngsparameter. På grund av modern sekretesspraxis är det här frågesträngsvärdet vanligtvis tomt. Adobe identifierar tomma nyckelordsfrågesträngar som en del av sökningsidentifieringen.
