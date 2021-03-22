---
title: getTimeToComplete
description: Mät hur lång tid det tar att slutföra en uppgift.
translation-type: tm+mt
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---


# Adobe plug-in: getTimeToComplete

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `getTimeToComplete` håller reda på hur lång tid det tar för en användare att slutföra en process på en webbplats. &quot;Klockan&quot; börjar när åtgärden `start` anropas och slutar när åtgärden `stop` anropas. Adobe rekommenderar att du använder denna plugin om det finns ett arbetsflöde på webbplatsen som tar lite tid att slutföra och du vill veta hur lång tid besökarna tar att slutföra det. Denna plugin behövs inte om arbetsflödet på webbplatsen tar kort tid (mindre än 3 sekunder) eftersom granulariteten bara är nere till en hel sekund.

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
   * Åtgärdstyp: Initiera getTimeToComplete
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getTimeToComplete` använder följande argument:

* **`sos`** (valfri, sträng): Ange  `"start"` när du vill starta timern. Ange `"stop"` när du vill stoppa timern. Standardvärdet är `"start"`.
* **`cn`** (valfri, sträng): Namnet på den cookie som ska lagra starttiden. Standardvärdet är `"s_gttc"`.
* **`exp`** (valfritt, heltal): Antalet dagar som cookien (och timern) förfaller. Standardvärdet är `0`, som representerar slutet av webbläsarsessionen.

När den här metoden anropas returneras en sträng som innehåller det antal dagar, timmar, minuter och/eller sekunder som det tog mellan åtgärden `"start"` och `"stop"`.

## Exempelanrop

### Exempel 1

Använd de här samtalen för att bestämma tiden mellan när en besökare påbörjar utcheckningsprocessen och när de gör ett köp.

Starta timern när besökaren startar utcheckningen:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Stoppa timern när besökaren gör köpet och ställ in prop1 på tidsskillnaden mellan stopp och start:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 fångar den tid som krävs för att slutföra inköpsprocessen

### Exempel 2

Om du vill att flera tidtagare ska köras samtidigt (för att mäta olika processer) måste du ange cookie-argumentet för cn manuellt.  Om du till exempel vill mäta hur lång tid som krävs för att slutföra ett köp ställer du in följande kod..

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...men om du vill mäta (samtidigt) hur lång tid det tar att fylla i ett registreringsformulär, kör du även följande kod:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

I det andra exemplet är event1 tänkt att fånga upp början av en registreringsprocess som kan ta upp till 7 dagar att slutföra, oavsett orsak, och event2 är avsedd att fånga upp slutförandet av registreringen.  s.prop2 fångar den tid som krävs för att slutföra registreringsprocessen

## Versionshistorik

### 4.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 3.1 (30 september 2019)

* Lagt till logik som kräver värdet start eller stop i det första argumentet.  Alla andra värden som skickas hindrar plugin-programmet från att köras.
* Uppdaterat `inList 2.0` plugin-program till `inList 2.1`.

### 3.0 (23 augusti 2018)

* Plugin-programmet `formatTime v1.0` har uppdaterats till `formatTime v1.1`.

### 3.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Mindre felkorrigeringar.

### 2.0 juni 21, 2016)

* Eliminerade beroendet av plugin-programmet `p_fo`.
* Kompatibilitet med H-kod och AppMeasurement har lagts till.
* Konsolloggning har lagts till.
