---
title: Sida
description: Sidans namn.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%

---


# Sida

Dimensionen Sida visar namnen på sidorna på din webbplats. Det är en av de vanligaste dimensionerna som används i Adobe Analytics, eftersom det ger insikt i vilka sidor på er webbplats som fungerar bäst.

Dimensionen är relaterad till [platsavsnittet](site-section.md) och [serverdimensionerna](server.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageName` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av `pageName` variabeln. Om variabeln inte är definierad återgår den till att använda sidans URL. `pageName`

## Dimensionsobjekt

Dimensionsobjekten innehåller namnen på sidorna på din plats. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder direkt `document.title`medan andra formulerar en anpassad felsökningsfunktion. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>I Rapporter och Analytics använder konverteringsstatistik linjär attribuering för den här dimensionen. Intäkterna delas till exempel mellan alla sidor som visas vid ett besök före en `purchase` händelse. Analysis Workspace använder den senaste attribueringen som standard, med möjlighet att använda vilken attribueringsmodell som helst.
