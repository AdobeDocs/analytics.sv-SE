---
title: inList
description: Kontrollera om ett värde finns i ett annat teckenavgränsat värde.
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Adobe plug-in: inList

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `inList` kan du kontrollera om ett värde redan finns i en avgränsad sträng eller i ett JavaScript-arrayobjekt. Flera andra plugin-program är beroende av att plugin-programmet `inList` fungerar. Denna plugin ger en tydlig fördel jämfört med JavaScript-metoden `indexOf()` där den inte matchar partiella strängar. Om du till exempel använde det här plugin-programmet för att kontrollera `"event2"` matchar det inte en sträng som innehåller `"event25"`. Denna plugin behövs inte om du inte behöver kontrollera värden i avgränsade strängar eller arrayer, eller om du vill använda din egen `indexOf()`-logik.

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera inList
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
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

Metoden `inList` använder följande argument:

* **`lv`** (required, string or array): En avgränsad lista med värden eller ett JavaScript-arrayobjekt som ska sökas igenom
* **`vtc`** (required, string): Värdet som ska sökas efter
* **`d`** (valfri, sträng): Avgränsaren som används för att separera enskilda värden i  `lv` argumentet. Standardvärdet är ett kommatecken (`,`) när inget anges.
* **`cc`** (valfritt, boolesk): Om det är inställt på  `true`görs en skiftlägeskänslig kontroll. Om `false` anges eller utelämnas görs en skiftlägesokänslig kontroll. Standardvärdet är `false`.

Om den här metoden anropas returneras `true` om en matchning hittas och `false` om det inte finns någon matchning.

## Exempelanrop

### Exempel 1

Om..

```js
s.events="event22,event24";
```

...och följande kod körs...

```js
if(s.inList(s.events,"event22"))
```

...villkorssatsen if är true

### Exempel 2

Om..

```js
s.events="event22,event24";
```

...och följande kod körs...

```js
if(s.inList(s.events,"event2"))
```

...villkorssatsen if är false eftersom anropet inList inte gav någon exakt matchning mellan event2 och något av de avgränsade värdena i s.events

### Exempel 2

Om..

```js
s.events="event22,event24";
```

...och följande kod körs...

```js
if(!s.inList(s.events,"event23"))
```

...villkorssatsen if är true eftersom anropet inList inte gav någon exakt matchning mellan event23 och något av de avgränsade värdena i s.events (observera operatorn NOT i början av variabelanropet inList).

### Exempel 4

Om..

```js
s.events = "event22,event23";
```

...och följande kod körs...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...villkorlig if-programsats är false.  Det här exemplet är inte praktiskt, men det visar att du måste använda försiktighet när du använder den skiftlägeskänsliga flaggan.

### Exempel 5

Om..

```js
s.linkTrackVars = "events,eVar1";
```

...och följande kod körs...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...villkorlig if-programsats är false.  Värdet på argumentet d som skickades till anropet (dvs. &quot;|&quot;) förutsätter att de enskilda värdena i s.linkTrackVars avgränsas av ett lodstreck, medan värdena i själva verket avgränsas med kommatecken.  I det här fallet försöker plugin-programmet matcha hela värdet för s.linkTrackVars (d.v.s. &quot;events,eVar1&quot;) och det värde som ska sökas efter (dvs. &quot;eVar1&quot;).

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v2.1 (26 september 2019)

* Alternativet för argumentet `cc` har lagts till så att det inte är booleskt. `1` är till exempel ett giltigt värde för ärendekontroll.

### v2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).

### v1.01 (27 september 2017)

* Optimerad kod för att minska storleken

### v1.0 (2009)

* Ursprunglig version.
