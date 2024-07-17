---
title: Korgar
description: Antalet träffar där en besökare lade till sin första produkt i en kundvagn.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---

# Korgar

Carts [metric](overview.md) visar antalet träffar där en besökare lade till sin första produkt i en kundvagn.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `scOpen` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Skillnaden mellan &quot;Carts&quot;, &quot;Cart views&quot; och &quot;Cart additions&quot;

Eftersom&quot;kundvagnar&quot;,&quot;kundvagnsvyer&quot; och&quot;kundvagnstillägg&quot; är händelser som kräver implementering, bestämmer din organisation den exakta skillnaden mellan dessa mätvärden. Adobe har dock utformat dessa värden för följande logik:

* Kundvagnar aktiveras endast en gång per köp när en besökare lägger till sin första produkt i kundvagnen.
* &quot;Vyer av kundvagnen&quot; utlöses varje gång en besökare visar sin kundvagn.
* &quot;Cart additions&quot;-utlösare för varje produkt som läggs till i kundvagnen.

När en kund lägger till sin första produkt i en kundvagn är det avsedda beteendet att utlösa både &quot;kundvagn&quot; och &quot;kundvagnstillägg&quot;. Återigen är dessa riktlinjer inte konkreta. Din organisation avgör den exakta implementeringslogiken.
