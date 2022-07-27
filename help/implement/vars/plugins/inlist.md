---
title: inList
description: Kontrollera om ett värde finns i ett annat teckenavgränsat värde.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Adobe plug-in: inList

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

The `inList` Med plugin-programmet kan du kontrollera om ett värde redan finns i en avgränsad sträng eller i ett JavaScript-arrayobjekt. Flera andra plugin-program är beroende av `inList` plugin-program som fungerar. Denna plugin ger en tydlig fördel jämfört med JavaScript-metoden `indexOf()` där det inte matchar partiella strängar. Om du t.ex. använde denna plugin för att kontrollera `"event2"`matchar den inte en sträng som innehåller `"event25"`. Denna plugin behövs inte om du inte behöver kontrollera värden i avgränsade strängar eller arrayer, eller om du vill använda en egen `indexOf()` logik.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize inList
1. Save and publish the changes to the rule.-->

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `inList` funktionen returnerar ett booleskt värde beroende på dess indata. Följande argument används:

* **`lv`** (required, string or array): En avgränsad lista med värden eller ett JavaScript-arrayobjekt som ska sökas igenom
* **`vtc`** (required, string): Värdet som ska sökas efter
* **`d`** (valfri, sträng): Avgränsaren som används för att separera enskilda värden i `lv` argument. Standardvärdet är ett komma (`,`) när den inte är inställd.
* **`cc`** (valfritt, boolesk): Om inställt på `true` eller `1`görs en skiftlägeskänslig kontroll. Om inställt på `false` eller utelämnas görs en skiftlägesokänslig kontroll. Standardvärdet är `false`.

Anrop till den här funktionen returnerar `true` om den hittar en matchning, och `false` om det inte hittar någon matchning.

## Exempel

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v2.1 (26 september 2019)

* Alternativet för `cc` -argument som inte ska vara booleskt. Till exempel: `1` är ett giltigt värde för ärendekontroll.

### v2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).

### v1.01 (27 september 2017)

* Optimerad kod för att minska storleken

### v1.0 (2009)

* Ursprunglig version.
