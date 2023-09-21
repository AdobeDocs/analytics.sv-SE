---
title: Enheter
description: Det totala antalet produkter som köpts i alla order.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Enheter

Enheter [mått](overview.md) visar det totala antalet produkter som köpts i alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsartiklar som bidrog till hur många produkter som köptes. Du kan till exempel se de bästa kampanjerna (med [Spårningskod](../dimensions/tracking-code.md) dimension) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som bidrog till köpta produkter.

## Hur det här måttet beräknas

För varje träff där `purchase` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel, summan av fältet &#39;Kvantitet&#39; i [`products`](/help/implement/vars/page-vars/products.md) variabel.

## Jämför order och enheter

The [Beställningar](orders.md) Endast mätvärden registrerar antalet inköpshändelser. Måttet Enheter är vanligtvis högre än Order eftersom kunderna kan köpa mer än en produkt. I dessa fall finns det en enda order med flera enheter.

Om du har beställningar som är större än enheter rekommenderar Adobe att du kontrollerar implementeringens integritet. Det är troligt att `products` variabeln är inte korrekt inställd på köp, vilket vanligtvis är oönskat beteende.
