---
title: Ta bort kundvagn
description: Antal träffar där en besökare tog bort en produkt från kundvagnen.
feature: Metrics
exl-id: 74b9677e-89c7-4409-8bd3-99707436def0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 0%

---

# Ta bort kundvagn

Cart removals [metric](overview.md) visar hur många gånger en besökare har tagit bort något från kundvagnen. Den här mätningen är användbar när du vill förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `scRemove` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md).
