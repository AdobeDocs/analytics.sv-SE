---
title: Server
description: Serverns namn.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 0%

---


# Server

Dimensionen Server anger vanligtvis webbplatsens värdnamn. För rapportsviter som kombinerar flera domäner eller underdomäner är den här dimensionen värdefull för att se vilka domäner eller underdomäner som fungerar bäst.

Dimensionen är relaterad till dimensionerna för [sid](page.md) - och [webbplatsavsnittet](site-section.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`server` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av [`server`](/help/implement/vars/page-vars/server.md) variabeln.

## Dimensionsvärden

Dimensionsvärdena inkluderar servrar på din plats. Din organisation avgör vilka specifika dimensionsvärden du vill använda. Vissa organisationer använder `window.location.hostname`medan andra formulerar egna värden. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
