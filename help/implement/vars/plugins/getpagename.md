---
title: getPageName
description: Skapa ett lättläst pageName från den aktuella webbplatssökvägen.
feature: Variables
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Adobe plug-in: getPageName

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

The `getPageName` plugin-programmet skapar en lättläst, användarvänlig formaterad version av den aktuella URL-adressen. Adobe rekommenderar att du använder denna plugin om du vill ha en [`pageName`](../page-vars/pagename.md) värde som är lätt att ställa in och förstå vid rapportering. Denna plugin behövs inte om du redan har en namnstruktur för `pageName` variabel, till exempel via ett datalager. Den används bäst när du inte har någon annan lösning för att ställa in `pageName` variabel.

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
    * Action Type: Initialize getPageName
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
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `getPageName` funktionen använder följande argument:

* **`si`** (valfri, sträng): Ett ID infogat i början av strängen som representerar platsens ID. Värdet kan antingen vara ett numeriskt ID eller ett eget namn. Om den inte anges används den aktuella domänen som standard.
* **`qv`** (valfri, sträng): En kommaavgränsad lista med frågesträngsparametrar som, om de finns i URL:en, läggs till i strängen
* **`hv`** (valfri, sträng): En kommaavgränsad lista med parametrar i URL-hash som, om de hittas i URL:en, läggs till i strängen
* **`de`** (valfri, sträng): Avgränsaren för att dela upp enskilda delar av strängen. Standardvärdet är ett rör (`|`).

Funktionen returnerar en sträng som innehåller en användarvänlig version av URL:en. Strängen tilldelas vanligtvis till `pageName` men kan även användas i andra variabler.

## Exempel

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## Uppgradera från tidigare versioner

Version 4.0+ av `getPageName` plug-in-programmet är inte beroende av att det finns ett AppMeasurement-objekt i Adobe Analytics (dvs. `s` -objekt). Om du uppgraderar till den här versionen ändrar du koden som anropar plugin-programmet genom att ta bort alla instanser av `s` objekt från anropet. Ändra till exempel `s.getPageName();` till `getPageName();`.

## Versionshistorik

### 4.2 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 4.1 (17 september 2019)

* Standardvärdet för avgränsare har ändrats till ett lodstreck (från kolon + blanksteg).

### 4.0 (22 maj 2018)

* Fullständig omanalys/omskrivning av plugin-program
