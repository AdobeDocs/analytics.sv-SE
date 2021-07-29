---
title: getPageName
description: Skapa ett lättläst pageName från den aktuella webbplatssökvägen.
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---

# Adobe plug-in: getPageName

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `getPageName` skapar en lättläst, användarvänlig formaterad version av den aktuella URL:en. Adobe rekommenderar att du använder det här plugin-programmet om du vill ha ett [`pageName`](../page-vars/pagename.md)-värde som är enkelt att ställa in och förstå vid rapportering. Denna plugin behövs inte om du redan har en namnstruktur för variabeln `pageName`, till exempel via ett datalager. Den används bäst när du inte har någon annan lösning för att ställa in variabeln `pageName`.

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getPageName
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getPageName` använder följande argument:

* **`si`** (valfri, sträng): Ett ID infogat i början av strängen som representerar platsens ID. Värdet kan antingen vara ett numeriskt ID eller ett eget namn. Om den inte anges används den aktuella domänen som standard.
* **`qv`** (valfri, sträng): En kommaavgränsad lista med frågesträngsparametrar som, om de finns i URL:en, läggs till i strängen
* **`hv`** (valfri, sträng): En kommaavgränsad lista med parametrar i URL-hash som, om de hittas i URL:en, läggs till i strängen
* **`de`** (valfri, sträng): Avgränsaren för att dela upp enskilda delar av strängen. Standardvärdet är en pipe (`|`).

Metoden returnerar en sträng som innehåller en användarvänlig version av URL:en. Den här strängen tilldelas vanligtvis till variabeln `pageName`, men kan även användas i andra variabler.

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

### Exempel 3

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

### Exempel 2

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

Version 4.0+ av plugin-programmet getPageName är inte beroende av om det finns ett AppMeasurement-objekt i Adobe Analytics (dvs.&quot;s&quot;-objektet) som ska köras.  Om du väljer att uppgradera till den här versionen måste du ändra koden som anropar plugin-programmet genom att ta bort alla instanser av s-objektet från anropet.
Ändra till exempel följande:

```js
s.pageName = s.getPageName();
```

...till detta:

```js
s.pageName = getPageName();
```

## Versionshistorik

### 4.2 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 4.1 (17 september 2019)

* Standardvärdet för avgränsare har ändrats till ett lodstreck (från kolon + blanksteg).

### 4.0 (22 maj 2018)

* Fullständig omanalys/omskrivning av plugin-program
