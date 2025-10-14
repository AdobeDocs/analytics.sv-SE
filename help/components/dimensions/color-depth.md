---
title: Färgdjup
description: Enhetens färgdjup.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Färgdjup

Färgdjupet [dimension](overview.md) visar hur många färger enheten stöder. Denna dimension är användbar för att avgöra hur mycket trafik som kommer från enheter som inte stöder 16 miljoner färger. Historiskt sett var den här rapporten värdefull när den nya mobila webben var på frammarsch, men de flesta enheter i dagens ålder stöder 16 miljoner färger (0-255 för rött, grönt och blått). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell och översätter bitvärdet till ett mer läsbart format. Den samlar in data från frågesträngen [`c` &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet använder variabeln `screen.colorDepth` för att fylla i frågesträngen för bildbegäran. Om du använder AppMeasurement (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt. Om du använder en datainsamlingsmetod utanför AppMeasurementet (till exempel via API:t), måste du ta med frågesträngsparametern `c` för varje träff med ett giltigt bitvärde.

## Dimensioner

Dimensionen innehåller det antal färger som stöds av enheten. Exempelvärden är `"16 million (24-bit)"`, `"16 million (32-bit)"` och `"65,536 (16-bit)"`. Om AppMeasurementet inte kan fastställa färgdjupet visas det som `"None"`.

>[!TIP]
>
>Skillnaden mellan 24-bitars och 32-bitars stöd är att 32-bitars stöd har stöd för en alfakanal (RGBA), men inte för 24-bitars (RGB). Mer information om det här konceptet finns i [Färgdjup](https://en.wikipedia.org/wiki/Color_depth) på Wikipedia.
