---
title: Sida
description: Sidans namn.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---


# Sida

Dimensionen Sida visar namnen på sidorna på din webbplats. Det är en av de vanligaste dimensionerna som används i Adobe Analytics, eftersom det ger insikter om vilka sidor på er webbplats som fungerar bäst.

Dimensionen är relaterad till [platsavsnittet](site-section.md) och [serverdimensionerna](server.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageName` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av `pageName` variabeln. Om variabeln inte är definierad återgår den till att använda sidans URL. `pageName`

## Dimensionsvärden

Dimensionsvärdena innehåller namnen på sidorna på din webbplats. Din organisation avgör vilka specifika dimensionsvärden du vill använda. Vissa organisationer använder direkt `document.title`medan andra formulerar en anpassad felsökningsfunktion. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

>[!NOTE] I Rapporter och analyser använder konverteringsstatistik linjär attribuering för den här dimensionen. Intäkterna delas till exempel mellan alla sidor som visas vid ett besök före en `purchase` händelse. Analysis Workspace använder den senaste attribueringen som standard, med möjlighet att använda vilken attribueringsmodell som helst.
