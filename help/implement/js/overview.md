---
title: AppMeasurement for JavaScript
description: Lär dig hur du implementerar Adobe Analytics med JavaScript utan ett tagghanteringssystem.
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---

# AppMeasurement for JavaScript

AppMeasurement for JavaScript har historiskt sett varit en vanlig metod för att implementera Adobe Analytics. Om tagghanteringssystemen är allt populärare bör du emellertid använda [taggar i Adobe Experience Platform](../launch/overview.md).

## Övergripande arbetsflöde för att skicka data till Adobe med JavaScript

1. Läs in filen `AppMeasurement.js`. Den här filen innehåller de bibliotek som krävs för att skicka data till Adobe.

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

3. Definiera sidnivåvariabler i webbplatsens sidkod. Variablerna avgör vilka mått och mätvärden som skickas till Adobe. Se [Sidvariabler](../vars/page-vars/page-variables.md) för en fullständig lista över variabler som du kan definiera.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. När alla sidnivåvariabler är definierade skickar du data till Adobe med metoden `t()`. Mer information finns i [t](../vars/functions/t-method.md).

   ```js
   s.t();
   ```
