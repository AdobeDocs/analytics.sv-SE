---
title: Server
description: Serverns namn.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 0%

---

# Server

Serverdimensionen [dimension](overview.md) visar vanligtvis webbplatsens värdnamn. För rapportsviter som kombinerar flera domäner eller underdomäner är den här dimensionen värdefull för att se vilka domäner eller underdomäner som fungerar bäst.

Den här dimensionen är relaterad till dimensionerna för [Sidan](page.md) och [webbplatsavsnittet](site-section.md). Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`server`-frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data med variabeln [`server`](/help/implement/vars/page-vars/server.md).

## Dimensioner

Bland Dimensionerna finns servrar på din plats. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder `window.location.hostname`, medan andra formulerar egna värden. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
