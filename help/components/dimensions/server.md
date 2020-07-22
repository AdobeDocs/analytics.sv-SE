---
title: Server
description: Serverns namn.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 0%

---


# Server

Dimensionen Server anger vanligtvis webbplatsens värdnamn. För rapportsviter som kombinerar flera domäner eller underdomäner är den här dimensionen värdefull för att se vilka domäner eller underdomäner som fungerar bäst.

Dimensionen är relaterad till dimensionerna för [sid](page.md) - och [webbplatsavsnittet](site-section.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`server` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av [`server`](/help/implement/vars/page-vars/server.md) variabeln.

## Dimensionsobjekt

Dimensionsobjekten inkluderar servrar på din plats. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder `window.location.hostname`medan andra formulerar egna värden. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
