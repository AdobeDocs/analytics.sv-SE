---
title: getPageName
description: Skapa ett lättläst pageName från den aktuella webbplatssökvägen.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getPageName

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin- `getPageName` programmet skapar en lättläst, användarvänlig formaterad version av den aktuella URL-adressen. Adobe rekommenderar att du använder denna plugin om du vill ha ett `pageName` värde som är enkelt att ställa in och förstå vid rapportering. Denna plugin behövs inte om du redan har en namnstruktur för variabeln, till exempel via ett datalager. `pageName` Den används bäst när du inte har någon annan lösning för att ställa in `pageName` variabeln.

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
   * Åtgärdstyp: Initiera getPageName
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
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getPageName`

* **`si`** (valfri, sträng): Ett ID infogat i början av strängen som representerar platsens ID. Värdet kan antingen vara ett numeriskt ID eller ett eget namn. Om den inte anges används den aktuella domänen som standard.
* **`qv`** (valfri, sträng): En kommaavgränsad lista med frågesträngsparametrar som, om de finns i URL:en, läggs till i strängen
* **`hv`** (valfri, sträng): En kommaavgränsad lista med parametrar i URL-hash som, om de hittas i URL:en, läggs till i strängen
* **`de`** (valfri, sträng): Avgränsaren för att dela upp enskilda delar av strängen. Standardvärdet är en pipe (`|`).

Metoden returnerar en sträng som innehåller en användarvänlig version av URL:en. Den här strängen tilldelas vanligtvis till `pageName` variabeln, men kan även användas i andra variabler.

## Exempelanrop

### Exempel 1

Om den aktuella URL:en var..

```js
https://mail.google.com/mail/u/0/#inbox
```

...och följande kod körs...

```js
s.pageName = getPageName()
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Exempel 2

Om den aktuella URL:en var..

```js
https://mail.google.com/mail/u/0/#inbox
```

...och följande kod körs...

```js
s.pageName = getPageName("gmail")
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "gmail|mail|u|0";
```

### Exempel 3

Om den aktuella URL:en var..

```js
https://www.google.com/
```

...och följande kod körs...

```js
s.pageName = getPageName()
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "www.google.com|home"
```

**Obs**: När koden körs på en URL som inte innehåller någon sökväg läggs värdet&quot;home&quot; alltid till i slutet av returvärdet

### Exempel 4

Om den aktuella URL:en var..

```js
https://www.google.com/
```

...och följande kod körs...

```js
s.pageName = getPageName("google","","","|")
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "google|home"
```

### Exempel 5

Om den aktuella URL:en var..

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...och följande kod körs...

```js
s.pageName = getPageName()
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Om följande kod körs i stället..

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...det slutliga värdet för s.pageName blir:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Uppgradera från tidigare versioner

Version 4.0+ av plugin-programmet getPageName är inte beroende av att det finns ett AppMeasurement-objekt i Adobe Analytics (dvs. objektet s) som ska köras.  Om du väljer att uppgradera till den här versionen måste du ändra koden som anropar plugin-programmet genom att ta bort alla instanser av s-objektet från anropet.
Ändra till exempel följande:

```js
s.pageName = s.getPageName();
```

...till detta:

```js
s.pageName = getPageName();
```

## Versionshistorik

### 4.1 (17 september 2019)

* Standardvärdet för avgränsare har ändrats till ett lodstreck (från kolon + blanksteg).

### 4.0 (22 maj 2018)

* Fullständig omanalys/omskrivning av plugin-program
