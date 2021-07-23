---
title: Migrera till AppMeasurement för JavaScript
description: Bestäm vad som behövs för att migrera implementeringen av H-koden.
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# Migrera till AppMeasurement för JavaScript

Om implementeringen fortfarande använder H Code rekommenderar Adobe starkt migrering till den senaste versionen av AppMeasurement. Du bör implementera Analytics via [taggar i Adobe Experience Platform](../launch/overview.md), men en uppdaterad JavaScript-implementering kan användas.

Följande betydande ändringar finns i AppMeasurement jämfört med H-koden:

* 3-7x snabbare än H Code.
* Ljusare än H-koden - 21 kB okomprimerad jämfört med H-koden, som är 33 kB okomprimerad.
* Biblioteket och sidkoden kan distribueras inuti taggen `<head>`.
* Befintlig H-kod på sidnivå är kompatibel med AppMeasurement.
* Biblioteket innehåller inbyggda verktyg för att hämta frågeparametrar, läsa och skriva cookies och utföra avancerad länkspårning.
* Biblioteket stöder inte dynamiska kontokonfigurationsvariabler (inklusive `dynamicAccountSelection`, `dynamicAccountMatch` och `dynamicAccountList`).

I följande steg beskrivs ett typiskt migreringsarbetsflöde.

1. **Hämta den nya AppMeasurement-filen**: Du kommer åt den nya filen genom att logga in på Adobe Analytics och sedan gå till Admin > All admin > Code Manager. Den hämtade komprimerade filen innehåller en minifierad `AppMeasurement.js`-fil, tillsammans med medie- och integreringsmoduler.
1. **Kopiera dina  `s_code.js` anpassningar till`AppMeasurement.js`**: Flytta all kod före  `DO NOT ALTER ANYTHING BELOW THIS LINE` avsnittet i  `s_code.js` till början av  `AppMeasurement.js`.
1. **Uppdatera alla plugin-program**: Kontrollera att du använder den senaste versionen av varje plugin-program som finns i  `s_code.js` filen. Detta inkluderar medie- och integreringsmodulerna.
1. **Distribuera filen** AppMeasurement.js: Överför  `AppMeasurement.js` filen till webbservern.
1. **Uppdatera skriptreferenser så att de pekar på`AppMeasurement.js`**: Se till att alla sidor refererar  `AppMeasurement.js` i stället för  `s_code.js`.

## Exempel på måttkod

En vanlig `AppMeasurement.js`-fil. Kontrollera att konfigurationsvariablerna är inställda ovanför funktionen `doPlugins`.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## Exempel på sidkod

Normal kod som läses in på varje sida.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Kontrollera att du även har tagit med en referens till `AppMeasurement.js` och `VisitorAPI.js` på varje sida. Mer information finns i [JavaScript-implementering](/help/implement/js/overview.md).
