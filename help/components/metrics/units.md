---
title: Enheter
description: Det totala antalet produkter som köpts i alla order.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Enheter

Måttet [Enheter](overview.md) visar det totala antalet produkter som köpts i alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsartiklar som bidrog till hur många produkter som köptes. Du kan till exempel se de främsta kampanjerna (med dimensionen [Spårningskod](../dimensions/tracking-code.md)) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som har bidragit till köpta produkter.

## Hur det här måttet beräknas

För varje träff där `purchase` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md) ska du summera fältet Kvantitet i variabeln [`products`](/help/implement/vars/page-vars/products.md).

## Jämför order och enheter

Måttet [Beställningar](orders.md) registrerar bara antalet inköpshändelser. Måttet Enheter är vanligtvis högre än Order eftersom kunderna kan köpa mer än en produkt. I dessa fall finns det en enda order med flera enheter.

Om du har beställningar som är större än enheter rekommenderar Adobe att du kontrollerar implementeringens integritet. Det är troligt att variabeln `products` inte är korrekt inställd på inköp, vilket vanligtvis är oönskat beteende.
