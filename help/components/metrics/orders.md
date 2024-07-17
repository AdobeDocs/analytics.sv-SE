---
title: Beställningar
description: Antal inköp.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Beställningar

[Måttet ](overview.md) för beställningar visar det totala antalet inköpshändelser som har gjorts på din webbplats. Detta mått är avgörande för e-handelsplatser när det gäller att mäta konvertering. Du kan kombinera det här måttet med valfri dimension för att se vilka dimensionsobjekt som har bidragit till en order. Du kan till exempel se de främsta kampanjerna (med dimensionen [Spårningskod](../dimensions/tracking-code.md)) eller de vanligaste interna söktermerna (med en [eVar](../dimensions/evar.md)) som har bidragit till inköp.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `purchase` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md).
