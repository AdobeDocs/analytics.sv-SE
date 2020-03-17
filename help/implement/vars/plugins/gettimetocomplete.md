---
title: getTimeToComplete
description: Mät hur lång tid det tar att slutföra en uppgift.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getTimeToComplete

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `getTimeToComplete` spårar den tid det tar för användaren att slutföra en process på en webbplats. &quot;Klockan&quot; börjar när `start` åtgärden anropas och slutar när `stop` åtgärden anropas. Adobe rekommenderar att du använder denna plugin om det finns ett arbetsflöde på webbplatsen som tar lite tid att slutföra och du vill veta hur lång tid besökarna tar att slutföra det. Denna plugin behövs inte om arbetsflödet på webbplatsen tar kort tid (mindre än 3 sekunder) eftersom granulariteten bara är nere till en hel sekund.

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
   * Åtgärdstyp: Initiera getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getTimeToComplete`

* **`sos`** (valfri, sträng): Ange till `"start"` när du vill starta timern. Ange till `"stop"` när du vill stoppa timern. Standardvärdet är `"start"`.
* **`cn`** (valfri, sträng): Namnet på den cookie som ska lagra starttiden. Standardvärdet är `"s_gttc"`.
* **`exp`** (valfritt, heltal): Antalet dagar som cookien (och timern) förfaller. Standardvärdet är `0`, vilket representerar slutet av webbläsarsessionen.

När den här metoden anropas returneras en sträng som innehåller det antal dagar, timmar, minuter och/eller sekunder som det tog mellan `"start"` åtgärden och `"stop"` åtgärden.

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

### 3.1 (30 september 2019)

* Lagt till logik som kräver värdet start eller stop i det första argumentet.  Alla andra värden som skickas hindrar plugin-programmet från att köras.
* Uppdaterat `inList 2.0` plugin-program till `inList 2.1`.

### 3.0 (23 augusti 2018)

* Plugin-programmet har `formatTime v1.0` uppdaterats till `formatTime v1.1`.

### 3.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Mindre felkorrigeringar.

### 2.0 juni 21, 2016)

* Eliminerade beroendet av `p_fo` plugin-programmet.
* Kompatibilitet med H-kod och AppMeasurement har lagts till.
* Konsolloggning har lagts till.
