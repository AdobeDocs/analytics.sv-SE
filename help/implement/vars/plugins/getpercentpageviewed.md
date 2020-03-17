---
title: getPercentPageViewed
description: Hämta den procentandel av sidan som besökaren visade.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe plug-in: getPercentPageViewed

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet mäter en besökares rullningsaktivitet för att se hur mycket av en sida de visar innan de går vidare till en annan sida. `getPercentPageViewed` Denna plugin behövs inte om sidorna är små i höjdled eller inte vill mäta rullningsaktiviteten.

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getPercentPageViewed`

* **`pid`** (valfri, sträng):  En sidbaserad identifierare som du kan korrelera med procentsatserna som anges i plugin-programmets mått.  Standardvärdet är `pageName` variabeln.
* **`ch`** (valfritt, boolesk):  Ange det här till `false` (eller `0`) om du inte vill att plugin-programmet ska ta hänsyn till ändringar som görs i sidstorleken efter den första inläsningen. Om det utelämnas används det här argumentet som standard `true`. Adobe rekommenderar att du i de flesta fall utelämnar det här argumentet.

Om metoden anropas returneras ingenting; i stället anges följande variabler:

* `s._ppvPreviousPage`: Namnet på föregående sida som visades. Slutliga rullningsmått för den aktuella sidan är inte tillgängliga förrän en ny sida har lästs in.
* `s._ppvHighestPercentViewed`: Den högsta procentandel av föregående sida som besökaren visade (höjdvis). Den längst punkten som besökaren rullade ned till på föregående sida.
* `s._ppvInitialPercentViewed`: Den procentandel av föregående sida som var synlig när föregående sida först lästes in.
* `s._ppvHighestPixelsSeen`: Det högsta antalet pixlar som visas (höjdvis) när besökaren rullade nedåt på föregående sida.
* `s._ppvFoldsSeen`: Det högsta antalet sidvikningar som nås när besökaren rullade nedåt på föregående sida. Den här variabeln innehåller &quot;top-of-page&quot;-vikningen.
* `s._ppvFoldsAvailable`: Det totala antalet&quot;sidvikningar&quot; som är tillgängliga för rullning nedåt på föregående sida.

Tilldela en eller flera av dessa variabler till eVars för att visa dimensionsdata i rapporter.

Denna plugin skapar en cookie `s_ppv` som heter förstahandsval och innehåller värdena ovan. Den förfaller i slutet av webbläsarsessionen.

## Exempelanrop

### Exempel 1

Följande kod...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Avgör om s.pageName anges och i så fall körs funktionen getPercentPageViewed i koden
* När funktionen getPercentPageViewed körs skapas de variabler som beskrivs i avsnittet &quot;Returnerar&quot; ovan
* Om variablerna &quot;Returns&quot; har angetts:
   * Koden ställer in s.prop1 lika med värdet för s._ppvPreviousPage (dvs. det föregående värdet för s.pageName eller föregående sida)
   * Koden ställer också in s.prop2 som lika med den högsta procentandelen som visades på föregående sida och den inledande procentandelen som visades på föregående sida, tillsammans med antalet vikningar som besökaren har nått och antalet vikningar som var tillgängliga

**Obs**:  Om en hel sida är synlig när den först läses in, blir både de högsta procentvärdena som visas och de inledande procentvärdena som visas lika med 100, och både folderna som visas och Tillgängliga blir lika med 1.   När en hel sida INTE är synlig när den först läses in, men besökaren aldrig rullar nedåt på sidan innan han/hon går till nästa sida, blir både de högsta procentvärdena visade och de inledande procentvärdena visade lika med samma värde.

### Exempel 2

Anta att s.prop5 har reserverats för att fånga en ifylld&quot;sidtyp&quot; i stället för hela sidnamnet.

Följande kod avgör om s.prop5 har ställts in och, i så fall, lagrar dess värde som &quot;föregående sida&quot; för att korrelera med dimensionerna Högsta procent visat och Inledande procent visat.  Värdet kommer fortfarande att lagras i variabeln s._ppvPreviousPage, men kan behandlas som om det vore föregående sidtyp i stället för föregående sidnamn.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Versionshistorik

### v4.0 (7 oktober 2019)

* Lagt till `s._ppvFoldsSeen` och `s._ppvFoldsAvailable` lösningar

### v3.01 (13 augusti 2018)

* Ett problem har korrigerats för sidor som har flera AppMeasurement-objekt på en sida

### v3.0 (13 april 2018)

* Point release (omkompilerad, mindre kodstorlek)
* Plugin-programmet skapar nu variabler som ska tilldelas Adobe Analytics-variabler i stället för returvärden
