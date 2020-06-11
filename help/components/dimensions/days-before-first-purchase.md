---
title: Dagar före första köpet
description: Antalet dagar mellan besökarens första besök och deras första inköp.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Dagar före första köpet

Dimensionen&quot;Dagar före första köp&quot; visar antalet dagar som går mellan första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionvärdet&quot;1 dag&quot;.

När en besökare har gjort sitt första köp tillhör de samma dimensionsvärde under resten av besökarens cookie-livstid.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i den här dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) händelsen i implementeringen. Om du implementerar `purchase` händelsen på din webbplats fungerar alltid den här dimensionen.

## Dimensionsvärden

Dimensionsvärdena omfattar antalet dagar mellan besökarens första besök på webbplatsen och deras första inköp. Varje antal dagar är ett separat dimensionsvärde, där&quot;samma dag&quot; inträffar där besökarens första besök och deras första köp sker samma dag.
