---
title: getTimeSinceLastVisit
description: Mät hur lång tid det tar mellan två besök.
exl-id: c5cef219-8a8a-4e57-a372-f2e063325a67
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# Adobe plug-in: getTimeSinceLastVisit

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getTimeSinceLastVisit` kan du spåra hur lång tid det har tagit för en besökare att återvända till din webbplats efter det senaste besöket.

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
   * Åtgärdstyp: Initiera getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v2.0 */
function getTimeSinceLastVisit(){if(arguments&&"-v"===arguments[0])return{plugin:"getTimeSinceLastVisit",version:"2.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.getTimeSinceLastVisit="2.0");window.formatTime=window.formatTime||function(c,b,d){function f(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var e="";"string"===typeof b&&"d"===b||("string"!==typeof b||!f("h,m,s",b))&&86400<=c?(b=86400,e="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!f("m,s",b))&&3600<=c?(b=3600,e="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!f("s",b))&&60<=c?(b=60,e="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,e="seconds",d=isNaN(d)?.2:b/d);e=Math.round(c*d/b)/d+" "+e;0===e.indexOf("1 ")&&(e=e.substring(0,e.length-1));return e}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var f=window.location.hostname,e=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){e=2<e?e:2;var k=f.lastIndexOf(".");if(0<=k){for(;0<=k&&1<e;)k=f.lastIndexOf(".",k-1),e--;k=0<k?f.substring(k):f}}g=k;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>f?b.length:f)))?c:""};h=new Date;var m=h.getTime(),n=cookieRead("s_tslv")||0,l=Math.round((m-n)/1E3);h.setTime(m+63072E6);cookieWrite("s_tslv",m,h);return n?1800<l||cookieRead("s_inv")?(cookieRead("s_inv")&&(l=cookieRead("s_inv")),cookieWrite("s_inv",l,30),"0"!==l?formatTime(l):"New Visitor"):"":(cookieWrite("s_inv","0",30),"New Visitor")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getTimeSinceLastVisit` använder inga argument. Den returnerar den tid som gått sedan besökaren senast kom till webbplatsen och som är paketerad i följande format:

* Tid mellan 30 minuter och en timme sedan det senaste besöket är inställt på närmaste halvminuters test. Exempel, `"30.5 minutes"`, `"53 minutes"`
* Tiden mellan en timme och en dag avrundas till närmaste kvartalstimme. Exempel, `"2.25 hours"`, `"7.5 hours"`
* Tiden som är större än en dag avrundas till närmsta dagstidsinställning. Exempel, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* Om en besökare inte har besökt tidigare eller om den förflutna tiden är längre än två år, anges värdet till `"New Visitor"`.

>[!NOTE]
>
>Denna plugin returnerar bara ett värde vid första besöket.

Denna plugin skapar en cookie från första part med namnet `"s_tslv"` som är inställd på en Unix-tidsstämpel för den aktuella tiden. Kakan går ut efter två års inaktivitet.

## Exempel

```js
// Given a visitor's first visit to the site
// Sets prop1 to "New Visitor"
s.prop1 = getTimeSinceLastVisit();

// 35 minutes later, the same visitor returns
// Sets prop1 to "35 minutes"
s.prop1 = getTimeSinceLastVisit();

// 4 days later, the same visitor returns
// Sets prop1 to "4 days"
s.prop1 = getTimeSinceLastVisit();
```

## Versionshistorik

### 2.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.0 (16 april 2018)

* Punktrelease (omkompilerad kod och mindre storlek).
* Kod som härletts från plugin-programmet `getDaysSinceLastVisit` (nu borttaget och ändrat namn).
* Använder nu `formatTime` och `inList` plugin-program för returvärdet.
