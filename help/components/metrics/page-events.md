---
title: Sidhändelser
description: Antalet utlösta länkspårningsåtgärder.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Sidhändelser

Sidhändelser [mått](overview.md) visar hur många gånger ett länkspårningsanrop gjordes. Den här mätningen är användbar när du vill veta vilka sidor som har det mest engagerande innehållet. Mätning för det här måttet är mest värdefullt när en besökare kan utföra en åtgärd på sidan utan att navigera till en ny sida.

Exempel: vid en vanlig resa på en e-handelsplats kan en besökare ha flera interaktioner på en sida. En vanlig Analytics-implementering har dessa interaktioner konfigurerade som länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)), medan en sidvy ([`t()`](/help/implement/vars/functions/t-method.md))-anropet är reserverat för den inledande sidinläsningen. Den här implementeringsmetoden ger avancerad händelsespårning som ger insikter om vilka interaktioner som sker innan en besökare fortsätter sin resa.

## Hur det här måttet beräknas

Det här måttet räknar alla länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) i en rapportsvit. Alla länktyper ingår i det här måttet, särskilt [Egna länkar](../dimensions/custom-link.md), [Hämta länkar](../dimensions/download-link.md)och [Avsluta länkar](../dimensions/exit-link.md). Den innehåller inga sidvisningsanrop ([`t()`](/help/implement/vars/functions/t-method.md)).

## Jämför med liknande mätvärden

* **Sidhändelser jämfört med [Sidvyer](page-views.md)**: Sidhändelser räknar antalet länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) och exkludera anrop till spårning av sidvy ([`t()`](/help/implement/vars/functions/t-method.md)). Sidvyer är motsatta. Antalet spårningsanrop för sidvyn räknas och länkar tas inte med.
