---
title: rfl
description: Ta bort ett specifikt värde från en teckenavgränsad sträng.
feature: Appmeasurement Implementation
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 0%

---

# Adobe plug-in: rfl (Remove From List)

{{plug-in}}

Med plugin-programmet `rfl` kan du ta bort värden från avgränsade strängar (till exempel [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md)) på ett säkert sätt. Denna plugin är användbar om du vill ta bort specifika värden från en avgränsad sträng utan att behöva oroa dig för avgränsare. Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

Plugin-programmet använder följande logik:

* Om värdet som du vill ta bort finns behåller plugin-programmet allt i variabeln utom värdet som ska tas bort.
* Om värdet som du vill ta bort inte finns behåller plugin-programmet den ursprungliga strängen som den är.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Inget
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för gemensam analys
   * Åtgärdstyp: Initiera offertförfrågan (ta bort från lista)
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken [!UICONTROL Configure tracking using custom code] som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `rfl` använder följande argument:

* **`lv`** (obligatoriskt, sträng): En variabel (eller sträng) som innehåller en lista med avgränsade värden
* **`vr`** (obligatoriskt, sträng): Det värde du vill ta bort från argumentet `lv`. Adobe rekommenderar att du inte tar bort flera värden under ett enskilt `rfl`-anrop.
* **`d1`** (valfri, sträng): Avgränsaren som argumentet `lv` använder. Standardvärdet är ett komma (`,`).
* **`d2`** (valfri sträng): Den avgränsare som du vill att retursträngen ska använda. Standardvärdet är samma värde som argumentet `d1`.
* **`df`** (valfritt, booleskt): Om `true` tvingas endast dubblettinstanser av argumentet `vr` från argumentet `lv` i stället för alla instanser. Standardvärdet är `false` när det inte anges.

När den här funktionen anropas returneras en modifierad sträng som innehåller argumentet `lv`, men utan instanser (eller dubblettinstanser) av värdet som anges i argumentet `vr`.

## Exempelanrop

### Exempel 1

Om..

```js
s.events = "event22,event24,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"event24");
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event26");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event24,event25";
```

I det här exemplet gjorde rfl-anropet inga ändringar i s.events eftersom s.events inte innehöll &quot;event26&quot;

### Exempel 3

Om..

```js
s.events = "event22,event24,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events);
```

... det slutliga värdet för s.events blir:

```js
s.events = "";
```

Om argumentet `lv` eller `vr` är tomma i ett `rfl`-anrop returnerar plugin-programmet ingenting.

### Exempel 4

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...slutvärdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

...men det slutliga värdet för s.eVar5 blir:

```js
s.eVar5 = "hello|today";
```

Tänk på att plugin-programmet bara returnerar ett värde. Det återställer inte variabeln som skickas via argumentet `lv`.

### Exempel 5

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.prop4 = rfl(s.prop4,"people");
```

...slutvärdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

Var noga med att ange argumentet `d1` i fall där argumentvärdet `lv` innehåller en annan avgränsare än standardvärdet (t.ex. komma).

### Exempel 6

Om..

```js
s.events = "event22,event23,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"EVenT23");
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event23");
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event23:12345");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event23:12345,event25";
```

När du behöver ta bort en händelse som använder serialisering och/eller numerisk syntax/valutasyntax, ska du bara ange själva händelsen (dvs. utan serialisering/numeriska/valutavärden) i anropet `rfl`.

### Exempel 9

Om..

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"event23");
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event23", "", "",true);
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event23", "", "|",true);
```

... det slutliga värdet för s.events blir:

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
s.events = rfl(s.events,"event23,event24");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event24,event25";
```

Det går inte att ange flera värden i argumentet `vr`. Logiken `rfl` i ovanstående exempel skulle först dela upp värdena i argumentet `lv` (dvs. s.events) och sedan försöka matcha varje avgränsat värde med det fullständiga argumentvärdet `vr` (dvs. `"event23,event24"`).

### Exempel 13

Om..

```js
s.events = "event22,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event25");
```

Varje värde som ska tas bort från listan ska finnas i ett eget `rfl`-anrop.

### Exempel 14

Om..

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...och följande kod körs...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

... det slutliga värdet för s.linkTrackVars blir:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

De tre sista argumenten (dvs. &quot;,&quot;,&quot;,&quot;,false) i slutet av det här `rfl`-anropet är inte nödvändiga, men skadar inte heller något eftersom de finns där eftersom de matchar standardinställningarna.

### Exempel 15

Om..

```js
s.events = "event22,event23,event24";
```

...och följande kod körs...

```js
rfl(s.events,"event23");
```

... det slutliga värdet av s.events kommer fortfarande att vara:

```js
s.events = "event22,event23,event24";
```

Kom ihåg att plugin-programmet bara returnerar ett värde. Det återställer inte variabeln som skickas via argumentet `lv`.

## Tidigare versioner

### 2.1 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01 (17 september 2019)

* Mindre felkorrigering för standardavgränsarvärdet

### 2.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Behovet av plugin-programmet `join` har tagits bort.

### 1.0 (18 juli 2016)

* Ursprunglig version.
