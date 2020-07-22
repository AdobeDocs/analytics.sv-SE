---
title: Beställningar
description: Antal inköp.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---


# Beställningar

Mätvärdet för &#39;Beställningar&#39; visar det totala antalet inköpshändelser som har gjorts på din webbplats. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsobjekt som har bidragit till en order. Du kan till exempel se de bästa kampanjerna (med [spårningskoddimensionen](../dimensions/tracking-code.md) ) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som har bidragit till inköp.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som `purchase` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabeln.
