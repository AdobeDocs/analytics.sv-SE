---
title: Sida
description: Sidans namn.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---


# Sida

Dimensionen Sida visar namnen på sidorna på din webbplats. Det är en av de vanligaste dimensionerna som används i Adobe Analytics, eftersom det ger dig insikt i vilka sidor på din webbplats som fungerar bäst.

Dimensionen är relaterad till [platsavsnittet](site-section.md) och [serverdimensionerna](server.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageName` frågesträngen](/help/implement/validate/query-parameters.md) i anrop till [sidvyn (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) tar alltid bort den här dimensionen, även om `pageName` frågesträngen finns.

AppMeasurement samlar in dessa data med hjälp av [`pageName`](/help/implement/vars/page-vars/pagename.md) variabeln. Om variabeln inte är definierad återgår den till att använda `pageName` [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabeln.

## Dimensioner

Dimensionen innehåller namnen på sidorna på webbplatsen. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder direkt `document.title`medan andra formulerar en anpassad felsökningsfunktion. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>I Rapporter och analyser använder konverteringsstatistik linjär attribuering för den här dimensionen. Intäkterna delas till exempel mellan alla sidor som visas vid ett besök före en `purchase` händelse. Analysis Workspace använder den senaste attribueringen som standard, med möjlighet att använda vilken attribueringsmodell som helst.
