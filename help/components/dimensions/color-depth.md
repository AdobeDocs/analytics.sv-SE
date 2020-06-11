---
title: Färgdjup
description: Enhetens färgdjup.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Färgdjup

Dimensionen Färgdjup visar hur många färger som enheten stöder. Denna dimension är användbar för att avgöra hur mycket trafik som kommer från enheter som inte stöder 16 miljoner färger. Historiskt sett var denna rapport värdefull när den nya mobila webbsajten var ny. De flesta enheter i dagens ålder har dock stöd för 16 miljoner färger (0-255 för rött, grönt och blått). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell och översätter bitvärdet till ett mer läsbart format. Den samlar in data från [`c` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement använder variabeln för att fylla i frågesträngen för bildbegäran. `screen.colorDepth` Om du använder AppMeasurement (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern för varje träff med ett giltigt bitvärde. `c`

## Dimensionsvärden

Dimensionsvärden är antalet färger som stöds av enheten. Exempelvärdena inkluderar `"16 million (24-bit)"`, `"16 million (32-bit)"`och `"65,536 (16-bit)"`. Om AppMeasurement inte kan fastställa färgdjupet visas det som `"None"`.

> [!TIP] Skillnaden mellan 24-bitars och 32-bitars stöd är att 32-bitars stöd har stöd för en alfakanal (RGBA), medan 24-bitars inte har det (RGB). Mer information om detta koncept finns i [Färgdjup](https://en.wikipedia.org/wiki/Color_depth) på Wikipedia.
