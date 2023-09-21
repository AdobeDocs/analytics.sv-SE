---
title: Intäkter
description: Det monetära beloppet för produkter som köpts på alla order.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# Intäkter

Intäkter [mått](overview.md) visar det monetära beloppet för produkter som köpts in på alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med vilken dimension som helst för att se vilka dimensionsartiklar som har bidragit till intäkterna. Du kan till exempel se de bästa kampanjerna (med [Spårningskod](../dimensions/tracking-code.md) dimension) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)).

## Hur det här måttet beräknas

För varje träff där `purchase` finns i [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variabel, summan av fältet &#39;Price&#39; i [`products`](/help/implement/vars/page-vars/products.md) variabel.

Det här måttet bygger på [currencyCode](/help/implement/vars/config-vars/currencycode.md) om valutan på sidan är en annan än rapportsvitens ursprungliga valuta.
