---
title: getTimeSinceLastVisit
description: Mät hur lång tid det tar mellan två besök.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getTimeSinceLastVisit

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getTimeSinceLastVisit` plugin-programmet kan du spåra hur lång tid det har tagit för en besökare att återvända till din webbplats efter det senaste besöket.

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
   * Åtgärdstyp: Initiera getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden använder inte några argument `getTimeSinceLastVisit` . Den returnerar den tid som gått sedan besökaren senast kom till webbplatsen och som är paketerad i följande format:

* Tid mellan 30 minuter och en timme sedan det senaste besöket är inställt på närmaste halvminuters test. Exempel, `"30.5 minutes"`, `"53 minutes"`
* Tiden mellan en timme och en dag avrundas till närmaste kvartalstimme. Exempel, `"2.25 hours"`, `"7.5 hours"`
* Tiden som är större än en dag avrundas till närmsta dagstidsinställning. Exempel, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* Om en besökare inte har besökt tidigare eller om den förflutna tiden är längre än två år, anges värdet till `"New Visitor"`.

> [!NOTE] Denna plugin returnerar bara ett värde vid första besöket.

Detta plugin-program skapar en cookie från första part med namnet `"s_tslv"` inställd på Unix-tidsstämpel för aktuell tid. Kakan går ut efter två års inaktivitet.

## Exempelanrop

### Exempel 1

Om en helt ny besökare kommer till webbplatsen och följande kod körs på första sidan av besöket ...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...värdet för s.prop1 anges som &quot;Ny besökare&quot;.

Om samma kod körs på samma domän efter 35 minuters inaktivitet, kommer värdet för s.prop1 att anges till &quot;35 minuter&quot;.

Om samma kod körs på samma domän efter 4 dagars ytterligare inaktivitet ställs värdet för s.prop1 in på &quot;4 dagar&quot;.

## Versionshistorik

### 1.0 (16 april 2018)

* Punktrelease (omkompilerad kod och mindre storlek).
* Kod härledd från `getDaysSinceLastVisit` plugin-programmet (nu borttaget och namnändrat).
* Använder nu `formatTime` och `inList` plugin-program för returvärdet.
