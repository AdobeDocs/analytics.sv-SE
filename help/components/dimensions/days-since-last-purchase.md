---
title: Dagar sedan senaste köp
description: Antalet dagar mellan den aktuella träffen och det senaste köpet de gjorde.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Dagar sedan senaste köp

Dagar sedan senaste köp [dimension](overview.md) mäter den tid som gått mellan besökarens aktuella träff och deras senaste köp vid den tidpunkten. Den här dimensionen hjälper dig att förstå det beteende besökare gör efter att ha köpt något på din webbplats.

Besökare som aldrig köpt något ingår inte i denna dimension. Dessutom kommer träffar som utlösts innan besökarens första inköp inte heller att inkluderas. Endast träffar efter besökarens första köp.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i den här dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md)-händelsen i din implementering. Om du implementerar `purchase`-händelsen på din webbplats fungerar alltid den här dimensionen.

## Dimensioner

Dimensioner omfattar antalet dagar mellan besökarens senaste köp och den aktuella träffen. Varje antal dagar är en separat dimensionspost där&quot;samma dag&quot; inträffar där besökarens senaste köp och den aktuella träffen inträffar samma dag.
