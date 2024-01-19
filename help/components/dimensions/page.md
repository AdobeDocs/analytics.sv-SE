---
title: Sida
description: Sidans namn.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Sida

Sidan [dimension](overview.md) listar namnen på sidorna på din webbplats. Det är en av de vanligaste dimensionerna som används i Adobe Analytics, eftersom det ger dig insikt i vilka sidor på din webbplats som fungerar bäst.

Den här dimensionen är relaterad till [Site section](site-section.md) och [Server](server.md) dimensioner. Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageName` frågesträng](/help/implement/validate/query-parameters.md) in [Anrop till sidvyn (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) alltid ta bort den här dimensionen, även om `pageName` frågesträngen finns.

AppMeasurementet samlar in dessa data med [`pageName`](/help/implement/vars/page-vars/pagename.md) variabel. Om `pageName` variabeln är inte definierad, den återgår till [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabel.

## Dimensioner

Dimensionen innehåller namnen på sidorna på webbplatsen. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder `document.title`medan andra formulerar en anpassad vägbeskrivningsfil. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i en [konstruktionsdokument](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace använder den senaste attribueringen som standard, med möjlighet att använda vilken attribueringsmodell som helst.
