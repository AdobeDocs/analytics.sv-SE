---
title: Sidhändelser
description: Antalet utlösta länkspårningsåtgärder.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Sidhändelser

Mätvärdet för Sidhändelser visar hur många gånger ett länkspårningsanrop gjordes. Den här mätningen är användbar när du vill veta vilka sidor som har det mest engagerande innehållet. Mätning för det här måttet är mest värdefullt när en besökare kan utföra en åtgärd på sidan utan att navigera till en ny sida.

## Hur det här måttet beräknas

Det här måttet räknar alla länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) i en rapportsvit. Alla länktyper ingår (anpassade länkar, hämtningslänkar och avslutningslänkar). Den innehåller inga anrop till spårning av sidvy ([`t()`](/help/implement/vars/functions/t-method.md)).

## Jämför med liknande mätvärden

* **Sidhändelser jämfört med [Sidvyer](page-views.md)**: Sidhändelser räknar antalet anrop för spårning av länkar (`tl()`) och utesluter anrop till spårning av sidvy (`t()`). Sidvisningar är motsatsen. antalet spårningsanrop för sidvy räknas och länkar utesluts.
