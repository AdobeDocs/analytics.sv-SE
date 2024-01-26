---
title: Variabla åsidosättningar
description: Med variabelåsidosättningar kan du ändra ett variabelvärde för ett enskilt spår eller spårlänksanrop.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---

# Variabla åsidosättningar

Med variabelåsidosättningar kan du ändra Analytics-värden för en enda träff utan att påverka befintliga variabler på sidan.

## Arbetsflöde

1. Skapa ett nytt JavaScript-objekt. Objektnamnet kan vara vad du vill.

   ```js
   var y = new Object();
   ```

2. Tilldela giltiga analysegenskaper till det här objektet:

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Använd objektet som ett argument i lämpligt spårningsanrop:

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

När ett spårningsanrop tar emot ett objekt i parametern overrides, skriver alla giltiga värden i åsidosättningsobjektet över värden i standardanalysobjektet. Variabler som redan har definierats i det befintliga Analytics-objektet påverkas inte.
