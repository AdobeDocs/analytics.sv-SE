---
title: getQueryParam
description: Extrahera värdet för en URL:s frågesträngsparameter.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# Adobe plug-in: getQueryParam

{{plug-in}}

The `getQueryParam` Med plugin-programmet kan du extrahera värdet för alla frågesträngsparametrar som finns i en URL. Det är användbart för att extrahera kampanjkoder, både interna och externa, från URL:er för landningssidor. Det är också värdefullt när du extraherar söktermer eller andra frågesträngsparametrar.

Detta plugin-program innehåller robusta funktioner för att analysera komplexa URL:er, inklusive hashvärden och URL:er som innehåller flera frågesträngsparametrar. Om du bara behöver ha en enkel frågesträngsparameter rekommenderar Adobe att du använder URL-parameterfunktionerna med hjälp av Web SDK eller Adobe Analytics-tillägget eller [`Util.getQueryParam()`](../functions/util-getqueryparam.md) som ingår i AppMeasurement.

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
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.-->

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `getQueryParam` funktionen använder följande argument:

* **`qsp`** (obligatoriskt): En kommaavgränsad lista med frågesträngsparametrar att söka efter i URL:en. Den är inte skiftlägeskänslig.
* **`de`** (valfritt): Den avgränsare som ska användas om flera frågesträngsparametrar matchar. Standardvärdet är en tom sträng.
* **`url`** (valfritt): En anpassad URL, sträng eller variabel som frågesträngens parametervärden ska extraheras från. Standardvärdet är `window.location`.

Om den här funktionen anropas returneras ett värde beroende på argumenten ovan och URL:en:

* Om ingen matchande frågesträngsparameter hittas returnerar funktionen en tom sträng.
* Om en matchande frågesträngsparameter hittas returnerar funktionen frågesträngsparameterns värde.
* Om en matchande frågesträngsparameter påträffas men värdet är tomt, returnerar funktionen `true`.
* Om flera matchande frågesträngsparametrar hittas returnerar funktionen en sträng med varje parametervärde avgränsat med strängen i `de` argument.

## Exempel

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## Versionshistorik

### 4.0.1 (26 mars 2021)

* Ett problem har uppdaterats där undefined returnerades i stället för &quot;&quot; om frågeparametern inte fanns i frågesträngen.

### 4.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.
* Tog bort beroenden för pt-plugin.

### 3.3 (24 september 2019)

* Onödig logik som minskar kodstorleken har ignorerats

### 3.2 (15 maj 2018)

* Flyttad `findParameterValue` och `getParameterValue` funktioner i `getQueryParam` function

### 3.1 (10 maj 2018)

* Ett problem med att hämta frågesträngsparametrar utan värde har korrigerats

### 3.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Ändrade namn på hjälpfunktioner till `findParameterValue` och `getParameterValue` för läsbarhet.
* Tog bort behovet av att lägga till ett argument för att hitta parametrar i URL-hash

### 2.5 (8 januari 2016)

* Kompatibel med både H-kod och AppMeasurement (kräver `s.pt` med AppMeasurement).

### 2.4

* Lagt till `h` -parameter, som gör att koden kan hitta frågesträngsparametrar som hittas efter hash (`#`)-tecken

### 2.3

* Korrigerade ett regressionsproblem där plugin-programmet bara fungerade när hashen fanns efter spårningskoden

### 2.2

* Tar nu bort hash-tecken (och allt efteråt) från returvärdet

### 2.1

* Kompatibel med H.10-kod
