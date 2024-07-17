---
title: Sida
description: Sidans namn.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Sida

Sidan [dimension](overview.md) visar namnen på sidorna på din webbplats. Det är en av de vanligaste dimensionerna som används i Adobe Analytics, eftersom det ger dig insikt i vilka sidor på din webbplats som fungerar bäst.

Dimensionen är relaterad till dimensionerna [Webbplatsavsnitt](site-section.md) och [Server](server.md). Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageName`-frågesträngen ](/help/implement/validate/query-parameters.md) i [sidvisningsanrop (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) tar alltid bort den här dimensionen, även om frågesträngen `pageName` finns.

AppMeasurementet samlar in dessa data med variabeln [`pageName`](/help/implement/vars/page-vars/pagename.md). Om variabeln `pageName` inte är inställd återgår den här dimensionen till att använda variabeln [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Dimensioner

Dimensionen innehåller namnen på sidorna på webbplatsen. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder `document.title` direkt, medan andra formulerar en anpassad felsökningsfunktion. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace använder den senaste attribueringen som standard, med möjlighet att använda vilken attribueringsmodell som helst.
