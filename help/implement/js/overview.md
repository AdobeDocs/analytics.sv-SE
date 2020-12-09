---
title: AppMeasurement for JavaScript
description: Lär dig hur du implementerar Adobe Analytics med JavaScript utan ett tagghanteringssystem.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# AppMeasurement for JavaScript

AppMeasurement for JavaScript har historiskt sett varit en vanlig metod för att implementera Adobe Analytics. Vi rekommenderar dock att [Adobe Experience Platform Launch](../launch/overview.md) används i allt större popularitet hos tagghanteringssystem.

## Övergripande arbetsflöde för att skicka data till Adobe med JavaScript

1. Läs in `AppMeasurement.js` filen. Den här filen innehåller de bibliotek som krävs för att skicka data till Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Definiera konfigurationsvariabler i `AppMeasurement.js`. När Analytics-objektet instansieras ser dessa variabler till att datainsamlingsinställningarna är korrekta. Se [Konfigurationsvariabler](../vars/config-vars/configuration-variables.md) för en fullständig lista över variabler som du kan definiera.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Definiera sidnivåvariabler i webbplatsens sidkod. Variablerna avgör vilka mått och mätvärden som skickas till Adobe. En fullständig lista med variabler som du kan definiera finns i [Sidvariabler](../vars/page-vars/page-variables.md) .

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. När alla sidnivåvariabler är definierade skickar du data till Adobe med `t()` metoden . See [t](../vars/functions/t-method.md) for more information.

   ```js
   s.t();
   ```
