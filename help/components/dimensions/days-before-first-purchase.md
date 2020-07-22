---
title: Dagar före första köpet
description: Antalet dagar mellan besökarens första besök och deras första inköp.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Dagar före första köpet

Dimensionen&quot;Dagar före första köp&quot; visar antalet dagar som går mellan första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionsposten&quot;1 dag&quot;.

När en besökare gör sitt första köp tillhör de samma dimensionsobjekt under resten av besökarens cookie-livstid.

## Fyll den här dimensionen med data

Adobe fyller automatiskt i den här dimensionen baserat på [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) händelsen i implementeringen. Om du implementerar `purchase` händelsen på din webbplats fungerar alltid den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten är antalet dagar mellan besökarens första besök på webbplatsen och deras första inköp. Varje antal dagar är en separat dimensionspost, där&quot;samma dag&quot; inträffar där en besökares första besök och deras första inköp sker samma dag.
