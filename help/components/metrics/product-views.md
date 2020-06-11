---
title: Produktvyer
description: Antalet vyer till produktsidor.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# Produktvyer

Mätvärdet för produktvisningar visar hur många gånger en produkt har visats. Det här måttet är användbart när du vill se de mest visade produkterna eller se hur den totala produktvyn ser ut över tiden.

## Hur det här måttet beräknas

Det här måttet räknar antalet träffar som matchar **något** av följande:

* Värdet `prodView` finns i [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabeln. eller
* Variabeln är inställd och det finns inga kundvagnshändelser i [`products`](/help/implement/vars/page-vars/products.md) `events` variabeln. Alla händelser som inte är anpassade (`event1` - `event1000`) är en kundvagnshändelse.