---
title: Numbers Suite
description: Producera och ändra tal för användning i andra JavaScript-variabler.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---


# Adobe plug-in: Numbers Suite

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Numbers Suite är en serie JavaScript-funktioner. Den innehåller följande plugin-program:

* **`zeroPad`**: Lägg till ett visst antal nollor i början av ett tal. Detta plugin-program är användbart om en variabel kräver ett visst antal siffror, t.ex. om du arbetar med JavaScript-datumobjekt och vill formatera datumets månad och dag med två siffror i stället för bara en siffra. I stället `01/09/2020` för `1/9/2020`.
* **`randomNumber`**: Generera ett slumpmässigt tal med ett visst antal siffror. Detta plugin-program är användbart om du distribuerar taggar från tredje part och vill ha ett slumpmässigt cachelagrat nummer.
* **`twoDecimals`**: Avrunda ett tal till hundradelsdelen av garderoben. Detta plugin-program är användbart för valutamaterial, så att du kan avrunda ett tal till ett giltigt valutavärde.

## Installera plugin-programmet med tillägget Adobe Experience Platform Launch

Adobe erbjuder ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installera och publicera [!UICONTROL Common Analytics Plugins] tillägget
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Vanliga Analytics-plugin-program
   * Åtgärdstyp: Initiera Numbers Suite
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

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmen

I metoden används följande argument: `zeroPad`

* **num** (obligatoriskt, heltal): Numret som ska fyllas ut. Metoden avrundar värdet för det här argumentet om det innehåller decimaler.
* **nod** (obligatoriskt, heltal): Antalet siffror i det slutliga returvärdet. Om numret som ska fyllas ut har färre siffror än antalet siffror att fylla i, läggs nollor till i början av `num` argumentet.

I metoden används följande argument: `randomNumber`

* **nod** (valfritt, heltal): Antalet siffror i det slumpmässiga tal som du vill generera. Maxvärdet är 17 siffror. Standardvärdet är 10 siffror.

I metoden används följande argument: `twoDecimals`

* **val** (required, number): Ett tal (som representeras av antingen en sträng eller ett nummerobjekt) som du vill avrunda till närmaste hundradel.

## Returnerar

* Metoden **zeroPad** returnerar en sträng som är lika med `num` argumentet, men med ett visst antal nollor som läggs till i början av värdet, vilket garanterar att returvärdet har rätt antal siffror.
* Metoden **randomNumber** returnerar en sträng som är lika med ett slumpmässigt tal med önskat antal siffror.
* Metoden **twoDecimals** returnerar ett sifferobjekt avrundat till närmaste hundradel.

## Exempelanrop

### zeroPad-exempel

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber-exempel

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### exempel på två decimaler

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Versionshistorik

### 1.0 (25 maj 2019)

* Ursprunglig version.
