---
title: Site section
description: Namnet på webbplatsavsnittet.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---

# Site section

I Site-avsnittet [dimension](overview.md) visas namnen på webbplatsens avsnitt. För stora webbplatser är det praktiskt att gruppera sidor i avsnitt. Den här dimensionen är användbar när du vill se de toppvisade eller högpresterande webbplatsavsnitten.

Dimensionen är relaterad till dimensionerna [Sida](page.md) och [Server](server.md). Sidan är mest granulerad, servern är minst granulerad och Site-avsnittet är mellan de två.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`ch`-frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data med variabeln [`channel`](/help/implement/vars/page-vars/channel.md).

## Dimensioner

Bland Dimensionerna finns namnen på webbplatsens avsnitt. Din organisation avgör vilka specifika dimensionsobjekt du vill använda. Oavsett vilken metod du använder måste du se till att den är konsekvent och att du spelar in den i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).
