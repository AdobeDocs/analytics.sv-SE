---
title: Dagar sedan senaste köp
description: Antalet dagar mellan den aktuella träffen och det senaste köpet de gjorde.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Dagar sedan senaste köp

Dimensionen Dagar sedan senaste köp mäter den tid som passerat mellan besökarens aktuella träff och deras senaste köp vid den tidpunkten. Den här dimensionen hjälper dig att förstå det beteende besökarna gör efter att ha köpt något på din webbplats.

Besökare som aldrig köpt något ingår inte i denna dimension. Dessutom kommer träffar som utlösts innan besökarens första inköp inte heller att inkluderas. Endast träffar efter besökarens första köp.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i den här dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) händelsen i implementeringen. Om du implementerar `purchase` händelsen på din webbplats fungerar alltid den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena omfattar antalet dagar mellan besökarens senaste köp och den aktuella träffen. Varje antal dagar är ett separat dimensionsvärde där&quot;samma dag&quot; inträffar där besökarens senaste köp och den aktuella träffen inträffar samma dag.
