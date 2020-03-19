---
title: getVisitNum
description: Spåra besökarens aktuella besöksnummer.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobe plug-in: getVisitNum

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet returnerar besöksnumret för alla besökare som kommer till webbplatsen inom det önskade antalet dagar. `getVisitNum` Analysis Workspace har en &#39;Besök Number&#39;-dimension som ger liknande funktioner. Adobe rekommenderar att du använder denna plugin om du vill ha mer kontroll över hur besöksnumret ökar. Denna plugin behövs inte om den inbyggda dimensionen &#39;Besök nummer&#39; i Analysis Workspace är tillräcklig för dina rapporteringsbehov.

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
   * Åtgärdstyp: Initiera getVisitNum
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

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getVisitNum`

* **`rp`** (valfritt, heltal ELLER sträng): Antalet dagar innan besöksnummerräknaren återställs.  Standardvärdet är `365` när det inte anges.
   * När det här argumentet är `"w"`återställs räknaren i slutet av veckan (den här lördagen klockan 11:59)
   * När det här argumentet är `"m"`återställs räknaren i slutet av månaden (den sista dagen i den här månaden)
   * När det här argumentet är `"y"`återställs räknaren i slutet av året (31 december)
* **`erp`** (valfritt, boolesk): När argumentet är ett tal avgör det här argumentet om giltigheten för besöksnumret ska förlängas. `rp` Om värdet är `true`återställs besöksnummerräknaren vid efterföljande träffar på webbplatsen. Om du väljer `false`det här alternativet utökas inte efterföljande träffar på din webbplats när besöksnummerräknaren återställs. Standardvärdet är `true`. Det här argumentet är inte giltigt när `rp` argumentet är en sträng.

Besöksnummerökningen när besökaren återvänder till er webbplats efter 30 minuters inaktivitet. Om den här metoden anropas returneras ett heltal som representerar besökarens aktuella besöksnummer.

Detta plugin-program ställer in en cookie från första part med namnet `"s_vnc[LENGTH]"` där `[LENGTH]` är värdet som skickas till `rp` argumentet. For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. Värdet för cookien är en kombination av en Unix-tidsstämpel som representerar när besöksräknaren återställs, till exempel slutet av veckan, slutet av månaden eller efter 365 dagars inaktivitet. Den innehåller även det aktuella besöksnumret. Detta plugin-program anger en annan cookie med namnet `"s_ivc"` som är inställd på `true` och upphör att gälla efter 30 minuters inaktivitet.

## Exempelanrop

### Exempel 1

För en besökare som inte har besökt webbplatsen inom de senaste 365 dagarna kommer följande kod att ställa in s.prop1 som lika med värdet 1:

```js
s.prop1=s.getVisitNum();
```

### Exempel 2

För en besökare som återvänder till webbplatsen inom 364 dagar efter sitt första besök kommer följande kod att ange s.prop1 till 2:

```js
s.prop1=s.getVisitNum(365);
```

Om besökaren återvänder till webbplatsen inom 364 dagar efter sitt andra besök, kommer följande kod att ange s.prop1 till 3:

```js
s.prop1=s.getVisitNum(365);
```

### Exempel 3

För en besökare som återvänder till webbplatsen inom 179 dagar efter sitt första besök kommer följande kod att ange s.prop1 till 2:

```js
s.prop1=s.getVisitNum(180,false);
```

Om besökaren återvänder till webbplatsen en eller flera dagar efter sitt andra besök, kommer följande kod att ställa in s.prop1 på 1:

```js
s.prop1=s.getVisitNum(180,false);
```

När det andra argumentet i anropet är lika med false kommer den rutin som bestämmer när besöksnumret ska vara &quot;återställt&quot; till 1 att göra &quot;x&quot; antal dagar - i det här exemplet 365 dagar - efter besökarens första besök på webbplatsen.

När det andra argumentet är lika med true (eller inte inställt alls) återställs besöksnumret till 1 först efter &quot;x&quot;-antalet dagar - i det här exemplet 365 dagar - besökarens inaktivitet.

### Exempel 4

För alla besökare som kommer till webbplatsen för första gången under den aktuella veckan - med början på söndagen - kommer följande kod att ställa in s.prop1 till 1:

```js
s.prop1=s.getVisitNum("w");
```

### Exempel 5

För alla besökare som kommer till webbplatsen för första gången under den aktuella månaden, med början den första dagen i varje månad, anges s.prop1 till 1:

```js
s.prop1=s.getVisitNum("m");
```

Kom ihåg att plugin-programmet getVisitNum inte tar hänsyn till butiksbaserade kalendrar (t.ex. 4-5-4, 4-4-5 osv.)

### Exempel 6

För alla besökare som kommer till webbplatsen för första gången under det aktuella året - med början den 1 januari - anges s.prop1 till 1:

```js
s.prop1=s.getVisitNum("y");
```

### Exempel 7

Om du vill spåra besökarens besöksnummer för veckan, besökarens besöksnummer för månaden och besökarens besöksnummer för året - allt inom olika analysvariabler - bör du använda kod som liknar följande:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

I det här fallet kommer plugin-programmet att skapa tre olika cookies - en för var och en av de olika tidsperioderna - för att hålla reda på besöksnumret per tidsperiod.

## Versionshistorik

### 4.11 (30 september 2019)

* Korrigerade ett problem där `erp` argumentet uttryckligen angavs till `false`.

### 4.1 (21 maj 2018)

* Plugin-programmet har uppdaterats till v1.1. `endOfDatePeriod`

### 4.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Tog bort cookie-argument eftersom plugin-programmet nu dynamiskt genererar cookies baserat på `rp` argumentet)

### 3.0 (5 juni 2016)

* fullständig översyn
* Kombinera alla tidigare lösningar som finns i olika versioner av `getVisitNum` plugin-programmet.
