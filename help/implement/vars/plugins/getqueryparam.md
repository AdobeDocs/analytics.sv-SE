---
title: getQueryParam
description: Extrahera värdet för en URL:s frågesträngsparameter.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getQueryParam

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getQueryParam` plugin-programmet kan du extrahera värdet för alla frågesträngsparametrar som finns i en URL. Det är användbart för att extrahera kampanjkoder, både interna och externa, från URL:er för landningssidor. Det är också värdefullt när du extraherar söktermer eller andra frågesträngsparametrar.

Detta plugin-program innehåller robusta funktioner för att analysera komplexa URL:er, inklusive hashvärden och URL:er som innehåller flera frågesträngsparametrar. Om du bara behöver ha enkla frågesträngsparametrar rekommenderar Adobe att du använder URL-parameterfunktionerna i Launch eller den metod som ingår i AppMeasurement. `Util.getQueryParam`

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
   * Åtgärdstyp: Initiera getQueryParam
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken så att [!UICONTROL Configure tracking using custom code] den visar [!UICONTROL Open Editor] knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getQueryParam`

* **`qsp`** (obligatoriskt): En kommaavgränsad lista med frågesträngsparametrar att söka efter i URL:en. Den är inte skiftlägeskänslig.
* **`de`** (valfritt): Den avgränsare som ska användas om flera frågesträngsparametrar matchar. Standardvärdet är en tom sträng.
* **`url`** (valfritt): En anpassad URL, sträng eller variabel som frågesträngens parametervärden ska extraheras från. Standardvärdet är `window.location`.

Om du anropar den här metoden returneras ett värde beroende på argumenten ovan och URL:en:

* Om ingen matchande frågesträngsparameter hittas returnerar metoden en tom sträng.
* Om en matchande frågesträngsparameter påträffas returnerar metoden frågesträngsparameterns värde.
* Om en matchande frågesträngsparameter påträffas men värdet är tomt, returnerar metoden `true`.
* Om flera matchande frågesträngsparametrar hittas returnerar metoden en sträng med varje parametervärde avgränsat med strängen i `de` argumentet.

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

### Exempel 2

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

Följande kod ställer in s.campaign som &quot;123456&quot;:

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

**Obs!** Plugin-programmet ersätter URL:en med hashtecknet för en kontroll med ett frågetecken om det inte finns något frågetecken.  Om URL:en innehåller ett frågetecken som kommer före hash-tecknet, kommer plugin-programmet att ersätta URL:en till Kontrollera hash-tecknet med ett et-tecken.

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

**Obs!** den tredje parametern kan vara en valfri sträng/variabel som koden använder för att söka efter frågesträngsparametrarna i

Följande kod ställer in s.eVar2 lika med &quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* Värdet 123456 kommer från parametern ecid i variabeln s.testURL
* Värdet för trackingcode1 kommer från parametern cid i variabeln s.testURL
* Värdet true kommer från förekomsten (men inte värdet) av parametern location efter hash-tecknet i variabeln s.testURL

Värdet 300 kommer från värdet på parametern pos i variabeln s.testURL

## Versionshistorik

### 3.3 (24 september 2019)

* Onödig logik som minskar kodstorleken har ignorerats

### 3.2 (15 maj 2018)

* Flyttad `findParameterValue` och `getParameterValue` funktioner till `getQueryParam` funktionen

### 3.1 (10 maj 2018)

* Ett problem med att hämta frågesträngsparametrar utan värde har korrigerats

### 3.0 (16 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Ändrade namn på hjälpfunktioner till `findParameterValue` och `getParameterValue` för läsbarhet.
* Tog bort behovet av att lägga till ett argument för att hitta parametrar i URL-hash

### 2.5 (8 januari 2016)

* Kompatibel med både H-kod och AppMeasurement (kräver `s.pt` AppMeasurement).

### 2.4

* Parametern har lagts till så att koden kan hitta frågesträngsparametrar som hittas efter hash-tecknet ( `h``#`)

### 2.3

* Korrigerade ett regressionsproblem där plugin-programmet bara fungerade när hashen fanns efter spårningskoden

### 2.2

* Tar nu bort hash-tecken (och allt efteråt) från returvärdet

### 2.1

* Kompatibel med H.10-kod
