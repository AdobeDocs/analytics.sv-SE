---
title: Produktvyer
description: Antalet vyer till produktsidor.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---

# Produktvyer

Mätvärdet för produktvisningar visar hur många gånger en produkt har visats. Det här måttet är användbart när du vill se de mest visade produkterna eller se hur den totala produktvyn ser ut över tiden.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar **antingen** av följande:

* Värdet `prodView` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel, eller
* The [`products`](/help/implement/vars/page-vars/products.md) variabeln har angetts och det finns inga shoppingvagnshändelser i `events` variabel. Alla händelser som inte är anpassade (`event1` - `event1000`) är en kundvagnsfest.
