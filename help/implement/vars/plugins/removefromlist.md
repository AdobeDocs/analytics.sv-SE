---
title: rfl
description: Ta bort ett specifikt värde från en teckenavgränsad sträng.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---

# Adobe plug-in: rfl (Ta bort från lista)

{{plug-in}}

The `rfl` Med plugin-programmet kan du&quot;säkert&quot; ta bort värden från avgränsade strängar, till exempel [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md)och andra. Denna plugin är användbar om du vill ta bort specifika värden från en avgränsad sträng utan att behöva oroa dig för avgränsare. Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

Plugin-programmet använder följande logik:

* Om värdet som du vill ta bort finns behåller plugin-programmet allt i variabeln utom värdet som ska tas bort.
* Om värdet som du vill ta bort inte finns behåller plugin-programmet den ursprungliga strängen som den är.

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
   * Åtgärdstyp: Initiera anbudsförfrågan (ta bort från lista)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `rfl` funktionen använder följande argument:

* **`lv`** (required, string): En variabel (eller sträng) som innehåller en lista med avgränsade värden
* **`vr`** (required, string): Värdet som du vill ta bort från `lv` argument. Adobe rekommenderar att du inte tar bort flera värden under en enda `rfl` ring.
* **`d1`** (valfri, sträng): Avgränsaren som `lv` -argument används. Standardvärdet är ett komma (`,`).
* **`d2`** (valfri, sträng): Avgränsaren som du vill att retursträngen ska använda. Standardvärdet är samma som `d1` argument.
* **`df`** (valfritt, boolesk): If `true`, framtvingar endast dubblettinstanser av `vr` argument från `lv` i stället för alla instanser. Standardvärdet är `false` när den inte är inställd.

Anrop till den här funktionen returnerar en modifierad sträng som innehåller `lv` -argument, men utan instanser (eller dubblettinstanser) av det värde som anges i `vr` argument.

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
s.events = rfl(s.events,"event26");
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
s.events = rfl(s.events);
```

...det slutliga värdet för s.events blir:

```js
s.events = "";
```

Om någon av `lv` argument `vr` argumentet är tomt i en `rfl` anrop, returnerar plugin-programmet ingenting.

### Exempel 4

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...det slutliga värdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

...men slutvärdet för s.eVar5 blir:

```js
s.eVar5 = "hello|today";
```

Tänk på att plugin-programmet bara returnerar ett värde. det inte &quot;återställer&quot; variabeln som skickas via `lv` argument.

### Exempel 5

Om..

```js
s.prop4 = "hello|people|today";
```

...och följande kod körs...

```js
s.prop4 = rfl(s.prop4,"people");
```

...det slutliga värdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people|today";
```

Var noga med att ange `d1` argument i de fall där `lv` argumentvärdet innehåller en annan avgränsare än standardvärdet (t.ex. komma).

### Exempel 6

Om..

```js
s.events = "event22,event23,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"EVenT23");
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
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23:12345");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23:12345,event25";
```

När du behöver ta bort en händelse som använder serialisering och/eller numerisk syntax/valutasyntax, bör du bara ange själva händelsen (dvs. utan serialisering/numeriska/valutavärden) i `rfl` ring.

### Exempel 9

Om..

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...och följande kod körs...

```js
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23", "", "",true);
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
s.events = rfl(s.events,"event23", "", "|",true);
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
s.events = rfl(s.events,"event23,event24");
```

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event24,event25";
```

Ställa in flera värden i `vr` argument stöds inte. The `rfl` logiken i ovanstående exempel skulle först dela upp värdena i `lv` argument (d.v.s. s.events) försöker sedan matcha varje avgränsat värde mot det fullständiga `vr` argumentvärde (dvs. `"event23,event24"`).

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

...det slutliga värdet för s.events blir:

```js
s.events = "event22,event25");
```

Varje värde som ska tas bort från listan bör finnas inom ett eget värde `rfl` ring.

### Exempel 14

Om..

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...och följande kod körs...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...det slutliga värdet för s.linkTrackVars blir:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

De tre sista argumenten (dvs. &quot;,&quot;,&quot;,&quot;,false) i slutet av detta `rfl` -anropet är inte nödvändigt, men gör inte heller något ont eftersom de finns där eftersom de matchar standardinställningarna.

### Exempel 15

Om..

```js
s.events = "event22,event23,event24";
```

...och följande kod körs...

```js
rfl(s.events,"event23");
```

...det slutliga värdet för s.events kommer fortfarande att vara:

```js
s.events = "event22,event23,event24";
```

Kom ihåg att plugin-programmet bara returnerar ett värde. det inte &quot;återställer&quot; variabeln som skickas via `lv` argument.

## Versionshistorik

### 2.1 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01 (17 september 2019)

* Mindre felkorrigering för standardavgränsarvärdet

### 2.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Behovet av `join` plugin-program.

### 1.0 (18 juli 2016)

* Ursprunglig version.
