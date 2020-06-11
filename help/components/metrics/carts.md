---
title: Korgar
description: Antalet träffar där en besökare lade till sin första produkt i en kundvagn.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---


# Korgar

Mätvärdet för kundvagnsborttagning visar hur många gånger en besökare har tagit bort något från sin kundvagn. Den här mätningen är användbar när du vill förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som `scOpen` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabeln.

## Skillnaden mellan kundvagnsvyer och kundvagnsvyer

Eftersom kundvagnar och kundvagnsvyer är händelser som kräver implementering avgör din organisation den exakta skillnaden mellan dessa två mätvärden. Adobe har dock utformat dessa mätvärden för följande:

* Kundvagnar aktiveras endast en gång per köp när en besökare lägger till sin första produkt i kundvagnen.
* &quot;Cart additions&quot;-utlösare för varje produkt som läggs till i kundvagnen.

För den första produkten utlöser både Carts och Cart additions. Återigen är dessa riktlinjer inte konkreta. organisationen bestämmer den exakta implementeringslogiken.
