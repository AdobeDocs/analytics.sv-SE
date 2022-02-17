---
title: Site section
description: Namnet på webbplatsavsnittet.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---

# Site section

Dimensionen Webbplatsavsnitt visar namnen på webbplatsavsnitten på din webbplats. För stora webbplatser är det praktiskt att gruppera sidor i avsnitt. Den här dimensionen är användbar när du vill se de toppvisade eller högpresterande webbplatsavsnitten.

Den här dimensionen är relaterad till [Sida](page.md) och [Server](server.md) dimensioner. Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`ch` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med [`channel`](/help/implement/vars/page-vars/channel.md) variabel.

## Dimensioner

Dimensionen innehåller namnen på webbplatsens avsnitt. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i en [konstruktionsdokument](/help/implement/prepare/solution-design.md).
