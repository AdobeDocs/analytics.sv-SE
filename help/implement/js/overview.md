---
title: AppMeasurement for JavaScript
description: Lär dig hur du implementerar Adobe Analytics med JavaScript utan ett tagghanteringssystem.
translation-type: tm+mt
source-git-commit: 59956169308291e7607a2712cd63a802d7b8bd11

---


# AppMeasurement for JavaScript

AppMeasurement for JavaScript har historiskt sett varit en vanlig metod för att implementera Adobe Analytics. Vi rekommenderar dock att du använder [Adobe Experience Platform Launch](../launch/overview.md) i allt större popularitet hos tagghanteringssystem.

## Övergripande arbetsflöde för att skicka data till Adobe med JavaScript

1. Läs in `AppMeasurement.js` filen. Filen innehåller de bibliotek som krävs för att skicka data till Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Definiera konfigurationsvariabler i `AppMeasurement.js`. När Analytics-objektet instansieras ser dessa variabler till att datainsamlingsinställningarna är korrekta. Se [Konfigurationsvariabler](../vars/config-vars/configuration-variables.md) för en fullständig lista över variabler som du kan definiera.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.omtrdc.net";
   ```

3. Definiera sidnivåvariabler i webbplatsens sidkod. Variablerna avgör vilka mått och mätvärden som skickas till Adobe. En fullständig lista med variabler som du kan definiera finns i [Sidvariabler](../vars/page-vars/page-variables.md) .

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. När alla sidnivåvariabler är definierade skickar du data till Adobe med `t` funktionen. Mer information [finns](../vars/functions/t-method.md) i den.

   ```js
   s.t();
   ```
