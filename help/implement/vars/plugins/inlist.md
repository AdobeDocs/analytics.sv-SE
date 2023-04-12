---
title: inList
description: Kontrollera om ett värde finns i ett annat teckenavgränsat värde.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Adobe plug-in: inList

{{plug-in}}

The `inList` Med plugin-programmet kan du kontrollera om ett värde redan finns i en avgränsad sträng eller i ett JavaScript-arrayobjekt. Flera andra plugin-program är beroende av `inList` plugin-program som fungerar. Denna plugin ger en tydlig fördel jämfört med JavaScript-metoden `indexOf()` där det inte matchar partiella strängar. Om du t.ex. använde denna plugin för att kontrollera `"event2"`matchar den inte en sträng som innehåller `"event25"`. Denna plugin behövs inte om du inte behöver kontrollera värden i avgränsade strängar eller arrayer, eller om du vill använda en egen `indexOf()` logik.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera inList
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

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
