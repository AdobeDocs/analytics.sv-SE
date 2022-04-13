---
title: Produktvyer
description: Antalet vyer till produktsidor.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: eb13c3e828bc6d4c547f4529ee7a15182bbbf046
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 0%

---

# Produktvyer

Mätvärdet för produktvisningar visar hur många gånger en produkt har visats. Det här måttet är användbart när du vill se de mest visade produkterna eller se hur den totala produktvyn ser ut över tiden.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar **antingen** av följande:

* Värdet `prodView` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabel, eller
* The [`products`](/help/implement/vars/page-vars/products.md) -variabeln är inställd och `events` variabeln är tom.
