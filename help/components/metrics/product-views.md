---
title: Produktvyer
description: Antalet vyer till produktsidor.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 0%

---

# Produktvyer

Produktvyerna [Mått](overview.md) visar antalet gånger som en produkt visades. Det här måttet är användbart när du vill se de mest visade produkterna eller se hur den totala produktvyn ser ut över tiden.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar **antingen** av följande:

* Värdet `prodView` finns i variabeln [`events`](/help/implement/vars/page-vars/events/events-overview.md) eller
* Variabeln [`products`](/help/implement/vars/page-vars/products.md) har angetts och variabeln `events` är tom.
