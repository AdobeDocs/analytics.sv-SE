---
title: rfl
description: Ta bort ett specifikt värde från en teckenavgränsad sträng.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: rfl (Ta bort från lista)

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `rfl` plugin-programmet kan du&quot;säkert&quot; ta bort värden från avgränsade strängar, till exempel `events`, `products`listvar och andra. Denna plugin är användbar om du vill ta bort specifika värden från en avgränsad sträng utan att behöva oroa dig för avgränsare. Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

Plugin-programmet använder följande logik:

* Om värdet som du vill ta bort finns behåller plugin-programmet allt i variabeln utom värdet som ska tas bort.
* Om värdet som du vill ta bort inte finns behåller plugin-programmet den ursprungliga strängen som den är.

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
   * Åtgärdstyp: Initiera anbudsförfrågan (ta bort från lista)
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

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med `s_gi`). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `rfl`

* **`lv`** (required, string): En variabel (eller sträng) som innehåller en lista med avgränsade värden
* **`vr`** (required, string): Värdet som du vill ta bort från `lv` argumentet. Adobe rekommenderar att du inte tar bort flera värden under ett enda `rfl` samtal.
* **`d1`** (valfri, sträng): Den avgränsare som används i `lv` argumentet. Standardvärdet är ett komma (`,`).
* **`d2`** (valfri, sträng): Avgränsaren som du vill att retursträngen ska använda. Standardvärdet är samma värde som `d1` argumentet.
* **`df`** (valfritt, boolesk): Om `true`det här alternativet används för att endast duplicera instanser av `vr` argumentet från `lv` argumentet i stället för alla instanser. Standardvärdet är `false` när det inte anges.

Om du anropar den här metoden returneras en modifierad sträng som innehåller `lv` argumentet, men utan instanser (eller dubblettinstanser) av värdet som anges i `vr` argumentet.

## Exempelanrop

### Exempel 1

Om..

```js
s.events = "event22,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event24");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event25";
```

### Exempel 2

Om..

```js
s.events = "event22,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event26");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event24,event25";
```

I det här exemplet har rfl-anropet inte gjort några ändringar i s.events eftersom s.events inte innehöll &quot;event26&quot;

### Exempel 3

Om..

```js
s.events = "event22,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events);
```

...det slutliga värdet för s.events blir:

```js
s.events = "";
```

Om argumentet lv eller vr är tomt i ett s.rfl-anrop returnerar plugin-programmet ingenting

### Exempel 4

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...det slutliga värdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

...men slutvärdet för s.eVar5 blir:

```js
s.eVar5 = "hello|today";
```

Tänk på att plugin-programmet bara returnerar ett värde. den&quot;återställer&quot; inte variabeln som skickas via lv-argumentet.

### Exempel 5

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...det slutliga värdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

Var noga med att ange argumentet d1 om värdet för lv-argumentet innehåller en annan avgränsare än standardvärdet (t.ex. komma).

### Exempel 6

Om..

```js
s.events = "event22,event23,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event25";
```

Även om det här exemplet inte är praktiskt visar det hur viktigt det är att skicka skiftlägeskänsliga värden.

### Exempel 7

Om..

```js
s.events = "event22,event23:12345,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event25";
```

### Exempel 8

Om..

```js
s.events = "event22,event23:12345,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23:12345,event25";
```

När du behöver ta bort en händelse som använder serialisering och/eller numerisk/valutasyntax, ska du bara ange själva händelsen (dvs. utan serialisering/numeriska/valutavärden) i s.rfl-anropet.

### Exempel 9

Om..

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event24,event25");
```

### Exempel 10

Om..

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event24,event25");
```

### Exempel 11

Om..

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22|event23|event24|event25");
```

### Exempel 12

Om..

```js
s.events = "event22,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event24,event25";
```

Det går inte att ange flera värden i vr-argumentet. Rfl-logiken i exemplet ovan skulle först dela upp värdena i lv-argumentet (dvs. s.events) och sedan försöka matcha varje avgränsat värde med det fullständiga VR-argumentvärdet (dvs. &quot;event23,event24&quot;).

### Exempel 13

Om..

```js
s.events = "event22,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event25");
```

Varje värde som ska tas bort från listan ska finnas i sitt eget s.rfl-anrop.

### Exempel 14

Om..

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...och följande kod körs...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...det slutliga värdet för s.linkTrackVars blir:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

De tre sista argumenten (dvs. &quot;,&quot;,&quot;,&quot;,false) i slutet av det här s.rfl-anropet är inte nödvändigt, men gör inte heller något illa eftersom de finns där eftersom de matchar standardinställningarna.

### Exempel 15

Om..

```js
s.events = "event22,event23,event24";
```

...och följande kod körs...

```js
s.rfl(s.events,"event23");
```

...det slutliga värdet för s.events kommer fortfarande att vara:

```js
s.events = "event22,event23,event24";
```

Kom ihåg att plugin-programmet bara returnerar ett värde. den&quot;återställer&quot; inte variabeln som skickas via lv-argumentet.

## Versionshistorik

### 2.01 (17 september 2019)

* Mindre felkorrigering för standardavgränsarvärdet

### 2.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Behovet av `join` plugin-programmet har tagits bort.

### 1.0 (18 juli 2016)

* Ursprunglig version.
