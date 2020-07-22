---
title: Site section
description: Namnet på webbplatsavsnittet.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Site section

Dimensionen Webbplatsavsnitt visar namnen på webbplatsavsnitten på din webbplats. För stora webbplatser är det praktiskt att gruppera sidor i avsnitt. Den här dimensionen är användbar när du vill se de toppvisade eller högpresterande webbplatsavsnitten.

Dimensionen är relaterad till dimensionerna [Sida](page.md) och [Server](server.md) . Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`ch` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av [`channel`](/help/implement/vars/page-vars/channel.md) variabeln.

## Dimensionsobjekt

Dimensionsobjekten innehåller namnen på webbplatsens avsnitt på din plats. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
