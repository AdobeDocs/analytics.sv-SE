---
title: Korgar
description: Antalet träffar där en besökare lade till sin första produkt i en kundvagn.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---

# Korgar

Mätvärdet &quot;Carts&quot; visar antalet träffar där en besökare lade till sin första produkt i en kundvagn.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar där `scOpen` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel.

## Skillnaden mellan kundvagnsvyer och kundvagnsvyer

Eftersom kundvagnar och kundvagnsvyer är händelser som kräver implementering avgör din organisation den exakta skillnaden mellan dessa två mätvärden. Adobe har dock utformat dessa mått för följande:

* Kundvagnar aktiveras endast en gång per köp när en besökare lägger till sin första produkt i kundvagnen.
* &quot;Cart additions&quot;-utlösare för varje produkt som läggs till i kundvagnen.

För den första produkten utlöser både Carts och Cart additions. Återigen är dessa riktlinjer inte konkreta. organisationen bestämmer den exakta implementeringslogiken.
