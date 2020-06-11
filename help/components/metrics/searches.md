---
title: Sökningar
description: Antal gånger en träff matchade externa sökvillkor.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---


# Sökningar

Måttet Sökningar visar antalet träffar som matchar Adobes externa sökidentifiering. Det här måttet är användbart när du vill titta på dimensionsvärden som inte är sökbara och se hur de har bidragit till sökmotortrafiken.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar Adobes externa sökidentifiering. Den måste överensstämma med båda följande:

* träffens referensvärde är en sökdomän som känns igen av Adobe
* Den refererande URL:en för träffen innehåller en nyckelordsfrågesträngsparameter. På grund av modern sekretesspraxis är det här frågesträngsvärdet vanligtvis tomt. Adobe identifierar tomma nyckelordsfrågesträngar som en del av sökningsidentifieringen.
