---
title: getVisitDuration
description: Spåra hur mycket tid en besökare har varit på webbplatsen hittills.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getVisitDuration

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin- `getVisitDuration` programmet håller reda på hur lång tid i minuter besökaren har varit på webbplatsen fram till den tidpunkten. Adobe rekommenderar att du använder denna plugin om du vill följa upp den kumulativa tiden på webbplatsen fram till den tidpunkten eller för att spåra den tid det tar att utföra en aktivitet. Denna plugin spårar inte tiden mellan händelser. om du vill ha den här funktionen använder du plugin-programmet `getTimeBetweenEvents` .

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
   * Åtgärdstyp: Initiera getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden använder inte några argument `getVisitDuration` . Det returnerar ett av följande värden:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (där `[x]` är antalet minuter som gått sedan besökaren landade på platsen)

Denna plugin skapar en cookie `"s_dur"`från första part som kallas antal millisekunder sedan besökaren landade på webbplatsen. Kakan går ut efter 30 minuters inaktivitet.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.eVar10 = s.getVisitDuration();
```

...anger alltid eVar10 som det antal minuter som gått sedan besökaren landade på platsen

### Exempel 2

Följande kod...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...I används plugin-programmet inList för att kontrollera om händelsvariabeln innehåller inköpshändelsen.  I så fall anges eVar10 som antalet minuter mellan besökarens början av besöket och tidpunkten för köpet.

### Exempel 3

Följande kod...

```js
s.prop10 = s.getVisitDuration();
```

...anger alltid prop10 som det antal minuter som gått sedan besökaren landade på platsen.  Detta är användbart om prop10 har målning aktiverad.  Om du lägger till mätvärdet för utgångar i prop10-rapporten visas en detaljerad rapport om hur lång tid det tog innan en besökare lämnade webbplatsen.

## Versionshistorik

### 2.0 (2 maj 2018)

* Point release (fullständig omanalys/omskrivning av plugin-program).
