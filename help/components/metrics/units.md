---
title: Enheter
description: Det totala antalet produkter som köpts i alla order.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# Enheter

Måttet Enheter visar det totala antalet produkter som köpts i alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsartiklar som bidrog till hur många produkter som köptes. Du kan till exempel se de bästa kampanjerna (med [spårningskod](../dimensions/tracking-code.md) ) eller de viktigaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som har bidragit till köpta produkter.

## Hur det här måttet beräknas

För varje träff som `purchase` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabeln, summan av fältet Kvantitet i [`products`](/help/implement/vars/page-vars/products.md) variabeln.

## Jämför order och enheter

Mätvärdet för [beställningar](orders.md) registrerar bara antalet inköpshändelser. Måttet Enheter är vanligtvis högre än Order eftersom kunderna kan köpa mer än en produkt. I dessa fall finns det en enda order med flera enheter.

Om du har beställningar som är högre än antalet enheter bör du kontrollera integriteten i implementeringen. Det är troligt att din `products` variabel inte är korrekt inställd på inköp, vilket vanligtvis är ett oönskat beteende.
