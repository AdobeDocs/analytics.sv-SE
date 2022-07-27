---
title: Numbers Suite
description: Producera och ändra tal för användning i andra JavaScript-variabler.
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Adobe plug-in: Numbers Suite

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Numbers Suite är en serie JavaScript-funktioner. Den innehåller följande plugin-program:

* **`zeroPad`**: Lägg till ett visst antal nollor i början av ett tal. Detta plugin-program är användbart om en variabel kräver ett visst antal siffror, t.ex. om du arbetar med JavaScript-datumobjekt och vill formatera datumets månad och dag med två siffror i stället för bara en siffra. Till exempel: `01/09/2020` i stället för `1/9/2020`.
* **`randomNumber`**: Generera ett slumpmässigt tal med ett visst antal siffror. Detta plugin-program är användbart om du distribuerar taggar från tredje part och vill ha ett slumpmässigt cachelagrat nummer.
* **`twoDecimals`**: Avrunda ett tal till hundradelsdelen av garderoben. Detta plugin-program är användbart för valutamaterial, så att du kan avrunda ett tal till ett giltigt valutavärde.

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
    * Action Type: Initialize Numbers Suite
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmen

The `zeroPad` funktionen använder följande argument:

* **num** (obligatoriskt, heltal): Numret som ska fyllas ut. Funktionen avrundar värdet för det här argumentet om det innehåller decimaler.
* **nod** (obligatoriskt, heltal): Antalet siffror i det slutliga returvärdet. Om siffran som ska fyllas på har färre siffror än antalet siffror att fylla i, lägger plugin-programmet till nollor i början av `num` argument.

The `randomNumber` funktionen använder följande argument:

* **nod** (valfritt, heltal): Antalet siffror i det slumpmässiga tal som du vill generera. Maxvärdet är 17 siffror. Standardvärdet är 10 siffror.

The `twoDecimals` funktionen använder följande argument:

* **val** (obligatoriskt, tal): Ett tal (som representeras av antingen en sträng eller ett nummerobjekt) som du vill avrunda till närmaste hundradel.

## Returnerar

* The **zeroPad** funktionen returnerar en sträng som är lika med `num` -argument men med ett visst antal nollor som läggs till i början av värdet, vilket garanterar att returvärdet har rätt antal siffror.
* The **randomNumber** returnerar en sträng som är lika med ett slumpmässigt tal med önskat antal siffror.
* The **twoDecimals** returnerar ett talobjekt avrundat till närmaste hundradel.

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
