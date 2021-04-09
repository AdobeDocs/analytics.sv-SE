---
title: getQueryParam
description: Extrahera värdet för en URL:s frågesträngsparameter.
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
translation-type: tm+mt
source-git-commit: 5a087087c8f54650173391bd7766bfdfd12ccb7e
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---

# Adobe plug-in: getQueryParam

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getQueryParam` kan du extrahera värdet för alla frågesträngsparametrar som finns i en URL. Det är användbart för att extrahera kampanjkoder, både interna och externa, från URL:er för landningssidor. Det är också värdefullt när du extraherar söktermer eller andra frågesträngsparametrar.

Detta plugin-program innehåller robusta funktioner för att analysera komplexa URL:er, inklusive hashvärden och URL:er som innehåller flera frågesträngsparametrar. Om du bara behöver ha en enkel frågesträngsparameter rekommenderar Adobe att du använder URL-parameterfunktionerna i Launch eller metoden [`Util.getQueryParam()`](../functions/util-getqueryparam.md) som ingår i AppMeasurement.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getQueryParam
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getQueryParam` använder följande argument:

* **`qsp`** (obligatoriskt): En kommaavgränsad lista med frågesträngsparametrar att söka efter i URL:en. Den är inte skiftlägeskänslig.
* **`de`** (valfritt): Den avgränsare som ska användas om flera frågesträngsparametrar matchar. Standardvärdet är en tom sträng.
* **`url`** (valfritt): En anpassad URL, sträng eller variabel som frågesträngens parametervärden ska extraheras från. Standardvärdet är `window.location`.

Om du anropar den här metoden returneras ett värde beroende på argumenten ovan och URL:en:

* Om ingen matchande frågesträngsparameter hittas returnerar metoden en tom sträng.
* Om en matchande frågesträngsparameter påträffas returnerar metoden frågesträngsparameterns värde.
* Om en matchande frågesträngsparameter påträffas men värdet är tomt returnerar metoden `true`.
* Om flera matchande frågesträngsparametrar hittas returnerar metoden en sträng med varje parametervärde avgränsat med strängen i `de`-argumentet.

## Exempelanrop

### Exempel 1

Om den aktuella URL:en är följande:

```js
http://www.abc123.com/?cid=trackingcode1
```

Följande kod ställer in s.campaign som lika med &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid');
```

### Exempel 3

Om den aktuella URL:en är följande:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Följande kod ställer in s.campaign som lika med &quot;trackingcode1:123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Exempel 3

Om den aktuella URL:en är följande:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Följande kod ställer in s.campaign som lika med &quot;trackingcode1123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Exempel 4

Om den aktuella URL:en är följande:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

Följande kod ställer in s.campaign till &quot;123456&quot;:

```js
s.campaign=s.getQueryParam('ecid');
```

### Exempel 5

Om den aktuella URL:en är följande:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

Följande kod ställer in s.campaign till &quot;123456&quot;

```js
s.campaign=s.getQueryParam('ecid');
```

**Obs!** Plugin-programmet ersätter URL:en med hash-tecknet med ett frågetecken om det inte finns något frågetecken.  Om URL:en innehåller ett frågetecken som kommer före hash-tecknet, kommer plugin-programmet att ersätta URL:en till Kontrollera hash-tecknet med ett et-tecken.

### Exempel 6

Om den aktuella URL:en är följande..

```js
http://www.abc123.com/
```

...och om variabeln s.testURL är inställd enligt följande:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

Följande kod kommer inte att ställa in s.campaign alls:

```js
s.campaign=s.getQueryParam('cid');
```

Följande kod ställer in s.campaign som &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Obs!** Den tredje parametern kan vara vilken sträng/variabel som helst som koden använder för att hitta frågesträngsparametrarna i

Följande kod ställer in s.eVar2 till &quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* Värdet 123456 kommer från parametern ecid i variabeln s.testURL
* Värdet för trackingcode1 kommer från parametern cid i variabeln s.testURL
* Värdet true kommer från förekomsten (men inte värdet) av parametern location efter hash-tecknet i variabeln s.testURL

Värdet 300 kommer från värdet på parametern pos i variabeln s.testURL

## Versionshistorik

### 4.0.1 (26 mars 2021)

* Ett problem har uppdaterats där undefined returnerades i stället för &quot;&quot; om frågeparametern inte fanns i frågesträngen.

### 4.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.
* Tog bort beroenden för pt-plugin.

### 3.3 (24 september 2019)

* Onödig logik som minskar kodstorleken har ignorerats

### 3.2 (15 maj 2018)

* Flyttade `findParameterValue`- och `getParameterValue`-funktionerna till funktionen `getQueryParam`

### 3.1 (10 maj 2018)

* Ett problem med att hämta frågesträngsparametrar utan värde har korrigerats

### 3.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Ändrade namn på hjälpfunktioner till `findParameterValue` och `getParameterValue` för läsbarhetssyften.
* Tog bort behovet av att lägga till ett argument för att hitta parametrar i URL-hash

### 2.5 (8 januari 2016)

* Kompatibel med både H-kod och AppMeasurement (kräver `s.pt` med AppMeasurement).

### 2.4

* Parametern `h` har lagts till, vilket gör att koden kan hitta frågesträngsparametrar som hittas efter hash-tecknet (`#`)

### 2.3

* Korrigerade ett regressionsproblem där plugin-programmet bara fungerade när hashen fanns efter spårningskoden

### 2.2

* Tar nu bort hash-tecken (och allt efteråt) från returvärdet

### 2.1

* Kompatibel med H.10-kod
