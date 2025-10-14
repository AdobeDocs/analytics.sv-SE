---
title: Beställningar
description: Antal inköp.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 0%

---

# Beställningar

[Måttet &#x200B;](overview.md) för beställningar visar det totala antalet inköpshändelser som har gjorts på din webbplats. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsobjekt som har bidragit till en order. Du kan till exempel se de främsta kampanjerna (med dimensionen [Spårningskod](../dimensions/tracking-code.md)) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som har bidragit till inköp.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `purchase` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md).
