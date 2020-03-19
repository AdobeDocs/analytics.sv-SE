---
title: inList
description: Kontrollera om ett värde finns i ett annat teckenavgränsat värde.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe plug-in: inList

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `inList` plugin-programmet kan du kontrollera om ett värde redan finns i en avgränsad sträng eller i ett JavaScript-arrayobjekt. Flera andra plugin-program är beroende av att `inList` plugin-programmet fungerar. Denna plugin ger en tydlig fördel jämfört med JavaScript-metoden `indexOf()` där den inte matchar partiella strängar. Om du till exempel använde det här plugin-programmet för att söka efter `"event2"`matchar det inte en sträng som innehåller `"event25"`. Denna plugin behövs inte om du inte behöver kontrollera värden i avgränsade strängar eller arrayer, eller om du vill använda din egen `indexOf()` logik.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe erbjuder ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installera och publicera [!UICONTROL Common Analytics Plugins] tillägget
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera inList
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken så att [!UICONTROL Configure tracking using custom code] den visar [!UICONTROL Open Editor] knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `inList`

* **`lv`** (required, string or array): En avgränsad lista med värden eller ett JavaScript-arrayobjekt som ska sökas igenom
* **`vtc`** (required, string): Värdet som ska sökas efter
* **`d`** (valfri, sträng): Avgränsaren som används för att separera enskilda värden i `lv` argumentet. Standardvärdet är ett kommatecken (`,`) när inget anges.
* **`cc`** (valfritt, boolesk): Om det är inställt på `true`görs en skiftlägeskänslig kontroll. Om inställningen är `false` eller utelämnas görs en skiftlägesokänslig kontroll. Standardvärdet är `false`.

Om den här metoden anropas returneras `true` om en matchning hittas och `false` om ingen matchning hittas.

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

### Exempel 3

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

### v2.1 (26 september 2019)

* Alternativet för att argumentet inte ska vara booleskt har lagts till `cc` . Exempel: `1` är ett giltigt värde för ärendekontroll.

### v2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).

### v1.01 (27 september 2017)

* Optimerad kod för att minska storleken

### v1.0 (2009)

* Ursprunglig version.


