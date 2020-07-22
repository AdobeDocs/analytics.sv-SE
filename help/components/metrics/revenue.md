---
title: Intäkter
description: Det monetära beloppet för produkter som köpts på alla order.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Intäkter

Måttet&quot;Intäkt&quot; visar det monetära beloppet för produkter som köpts in på alla order. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med vilken dimension som helst för att se vilka dimensionsartiklar som har bidragit till intäkterna. Du kan till exempel se de bästa kampanjerna (med [spårningskoddimensionen](../dimensions/tracking-code.md) ) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)).

## Hur det här måttet beräknas

För varje träff som `purchase` finns i [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variabeln, summerar du&quot;Price&quot;-fältet i [`products`](/help/implement/vars/page-vars/products.md) variabeln.

Det här måttet är beroende av variabeln [currencyCode](/help/implement/vars/config-vars/currencycode.md) om valutan på sidan är en annan än rapportsvitens ursprungliga valuta.
