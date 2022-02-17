---
title: Beställningar
description: Antal inköp.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---

# Beställningar

Mätvärdet för &#39;Beställningar&#39; visar det totala antalet inköpshändelser som har gjorts på din webbplats. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsobjekt som har bidragit till en order. Du kan till exempel se de bästa kampanjerna (med [Spårningskod](../dimensions/tracking-code.md) dimension) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som bidrog till inköp.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `purchase` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel.
