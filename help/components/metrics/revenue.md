---
title: Intäkter
description: Det monetära beloppet för produkter som köpts på alla order.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# Intäkter

Inkomstmåttet [&#128279;](overview.md) visar det monetära beloppet för produkter som köpts in i alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med vilken dimension som helst för att se vilka dimensionsartiklar som har bidragit till intäkterna. Du kan till exempel se de främsta kampanjerna (med dimensionen [Spårningskod](../dimensions/tracking-code.md)) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)).

## Hur det här måttet beräknas

För varje träff där `purchase` finns i variabeln [`events`](/help/implement/vars/page-vars/events/event-purchase.md) ska du summera fältet Price i variabeln [`products`](/help/implement/vars/page-vars/products.md).

Det här måttet är beroende av variabeln [currencyCode](/help/implement/vars/config-vars/currencycode.md) om valutan på sidan skiljer sig från rapportsvitens ursprungliga valuta.
