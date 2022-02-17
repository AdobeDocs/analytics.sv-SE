---
title: Färgdjup
description: Enhetens färgdjup.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Färgdjup

Dimensionen Färgdjup visar hur många färger som enheten stöder. Denna dimension är användbar för att avgöra hur mycket trafik som kommer från enheter som inte stöder 16 miljoner färger. Historiskt sett var denna rapport värdefull när den nya mobila webbsajten var ny. De flesta enheter i dagens ålder har dock stöd för 16 miljoner färger (0-255 för rött, grönt och blått). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell och översätter bitvärdet till ett mer läsbart format. Den samlar in data från [`c` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement använder `screen.colorDepth` variabel för att fylla i frågesträngen för bildbegäran. Om du använder AppMeasurement (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med `c` frågesträngsparameter för varje träff med ett giltigt bitvärde.

## Dimensioner

Dimensionen innehåller det antal färger som stöds av enheten. Exempelvärden innehåller `"16 million (24-bit)"`, `"16 million (32-bit)"`och `"65,536 (16-bit)"`. Om AppMeasurement inte kan fastställa färgdjupet visas det som `"None"`.

>[!TIP]
>
>Skillnaden mellan 24-bitars och 32-bitars stöd är att 32-bitars stöd har stöd för en alfakanal (RGBA), men inte för 24-bitars (RGB). Se [Färgdjup](https://en.wikipedia.org/wiki/Color_depth) på Wikipedia för mer information om detta koncept.
