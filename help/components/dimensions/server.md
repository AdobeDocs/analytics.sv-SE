---
title: Server
description: Serverns namn.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 0%

---

# Server

Dimensionen Server anger vanligtvis webbplatsens värdnamn. För rapportsviter som kombinerar flera domäner eller underdomäner är den här dimensionen värdefull för att se vilka domäner eller underdomäner som fungerar bäst.

Den här dimensionen är relaterad till [Sida](page.md) och [Site section](site-section.md) dimensioner. Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`server` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med [`server`](/help/implement/vars/page-vars/server.md) variabel.

## Dimensioner

Bland Dimensionerna finns servrar på din plats. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Vissa organisationer använder `window.location.hostname`medan andra formulerar egna värden. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i en [konstruktionsdokument](/help/implement/prepare/solution-design.md).
