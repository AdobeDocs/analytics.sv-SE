---
title: Sidhändelser
description: Antalet utlösta länkspårningsåtgärder.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Sidhändelser

Sidhändelser [mått](overview.md) visar hur många gånger ett länkspårningsanrop gjordes. Den här mätningen är användbar när du vill veta vilka sidor som har det mest engagerande innehållet. Mätning för det här måttet är mest värdefullt när en besökare kan utföra en åtgärd på sidan utan att navigera till en ny sida.

## Hur det här måttet beräknas

Det här måttet räknar alla [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) i en rapportsvit. Alla länktyper ingår (anpassade länkar, hämtningslänkar och avslutningslänkar). Den innehåller inte [Spårningsanrop för sidvy (`t()`)](/help/implement/vars/functions/t-method.md).

## Jämför med liknande mätvärden

* **Sidhändelser jämfört med [Sidvyer](page-views.md)**: Sidhändelser räknar antalet länkspårningsanrop (`tl()`) och exkludera anrop till spårning av sidvy (`t()`). Sidvyer är motsatta. Antalet spårningsanrop för sidvyn räknas och länkar tas inte med.
