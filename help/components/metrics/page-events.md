---
title: Sidhändelser
description: Antalet utlösta länkspårningsåtgärder.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Sidhändelser

Mätvärdet för Sidhändelser visar hur många gånger ett länkspårningsanrop gjordes. Den här mätningen är användbar när du vill veta vilka sidor som har det mest engagerande innehållet. Mätning för det här måttet är mest värdefullt när en besökare kan utföra en åtgärd på sidan utan att navigera till en ny sida.

## Hur det här måttet beräknas

Det här måttet räknar alla länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) i en rapportserie. Alla länktyper ingår (anpassade länkar, hämtningslänkar och avslutningslänkar). Det omfattar inte spårningsanrop för sidvy ([`t()`](/help/implement/vars/functions/t-method.md)).

## Jämför med liknande mätvärden

* **Sidhändelser jämfört med[sidvyer](page-views.md)**: Sidhändelser räknar antalet anrop för spårning av länkar (`tl()`) och utesluter anrop för spårning av sidvy (`t()`). Sidvisningar är motsatsen. antalet spårningsanrop för sidvy räknas och länkar utesluts.
