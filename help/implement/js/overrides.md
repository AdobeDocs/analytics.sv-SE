---
title: Variabla åsidosättningar
description: Med variabelåsidosättningar kan du ändra ett variabelvärde för ett enskilt spår eller spårlänksanrop.
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

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

När ett spårningsanrop tar emot ett objekt i parametern overrides, skriver alla giltiga värden i åsidosättningsobjektet över värden i standardanalysobjektet. Variabler som redan definierats i det befintliga Analytics-objektet påverkas inte.
