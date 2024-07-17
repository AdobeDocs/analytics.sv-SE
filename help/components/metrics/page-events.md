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

Sidhändelserna [Mått](overview.md) visar hur många gånger ett länkspårningsanrop gjordes. Den här mätningen är användbar när du vill veta vilka sidor som har det mest engagerande innehållet. Mätning för det här måttet är mest värdefullt när en besökare kan utföra en åtgärd på sidan utan att navigera till en ny sida.

Exempel: vid en vanlig resa på en e-handelsplats kan en besökare ha flera interaktioner på en sida. En vanlig Analytics-implementering har konfigurerat dessa interaktioner som ett länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)), medan ett sidvyanrop ([`t()`](/help/implement/vars/functions/t-method.md)) är reserverat för den inledande sidinläsningen. Den här implementeringsmetoden ger avancerad händelsespårning som ger insikter om vilka interaktioner som sker innan en besökare fortsätter sin resa.

## Hur det här måttet beräknas

Det här måttet räknar alla länkspårningsanrop ([`tl()`](/help/implement/vars/functions/tl-method.md)) i en rapportserie. Alla länktyper ingår i det här måttet, särskilt [Anpassade länkar](../dimensions/custom-link.md), [Hämta länkar](../dimensions/download-link.md) och [Avsluta länkar](../dimensions/exit-link.md). Det innehåller inga sidvisningsanrop ([`t()`](/help/implement/vars/functions/t-method.md)).

## Jämför med liknande mätvärden

* **Sidhändelser kontra [Sidvyer](page-views.md)**: Sidhändelser räknar antalet anrop för länkspårning ([`tl()`](/help/implement/vars/functions/tl-method.md)) och utesluter anrop för sidvyspårning ([`t()`](/help/implement/vars/functions/t-method.md)). Sidvyer är motsatta. Antalet spårningsanrop för sidvyn räknas och länkar tas inte med.
