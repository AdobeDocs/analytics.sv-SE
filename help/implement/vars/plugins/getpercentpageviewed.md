---
title: getPercentPageViewed
description: Hämta den procentandel av sidan som besökaren visade.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: f37348c549904933b4d84c8bf71c00e72e38b026
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 0%

---

# Adobe plug-in: getPercentPageViewed

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `getPercentPageViewed` mäter en besökares rullningsaktivitet för att se hur mycket av en sida de visar innan de går vidare till en annan sida. Denna plugin behövs inte om sidorna är små i höjdled eller inte vill mäta rullningsaktiviteten.

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
   * Åtgärdstyp: Initiera getPercentPageViewed
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:encodeURIComponent(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0.1"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getPercentPageViewed` använder följande argument:

* **`pid`** (valfri, sträng): En sidbaserad identifierare som du kan korrelera med procentsatserna som anges i plugin-programmets mått.  Standardvärdet är variabeln `pageName`.
* **`ch`** (valfritt, boolesk): Ange det här till  `false` (eller  `0`) om du inte vill att plugin-programmet ska ta hänsyn till ändringar som görs i sidstorleken efter den första inläsningen. Om det utelämnas blir det här argumentet som standard `true`. Adobe rekommenderar att detta argument utelämnas i de flesta fall.

Om metoden anropas returneras ingenting; i stället anges följande variabler:

* `s._ppvPreviousPage`: Namnet på föregående sida som visades. Slutliga rullningsmått för den aktuella sidan är inte tillgängliga förrän en ny sida har lästs in.
* `s._ppvHighestPercentViewed`: Den högsta procentandel av föregående sida som besökaren visade (höjdvis). Den längst punkten som besökaren rullade ned till på föregående sida.
* `s._ppvInitialPercentViewed`: Den procentandel av föregående sida som var synlig när föregående sida först lästes in.
* `s._ppvHighestPixelsSeen`: Det högsta antalet pixlar som visas (höjdvis) när besökaren rullade nedåt på föregående sida.
* `s._ppvFoldsSeen`: Det högsta antalet sidvikningar som nås när besökaren rullade nedåt på föregående sida. Den här variabeln innehåller &quot;top-of-page&quot;-vikningen.
* `s._ppvFoldsAvailable`: Det totala antalet&quot;sidvikningar&quot; som är tillgängliga för rullning nedåt på föregående sida.

Tilldela en eller flera av dessa variabler till eVars för att visa dimensionsdata i rapporter.

Detta plugin-program skapar en cookie från första part med namnet `s_ppv` som innehåller ovanstående värden. Den förfaller i slutet av webbläsarsessionen.

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

**Obs**: Om en hel sida är synlig när den först läses in, blir både de högsta procentvärdena som visas och de inledande procentvärdena som visas lika med 100, och både folderna som visas och Tillgängliga blir lika med 1.   När en hel sida INTE är synlig när den först läses in, men besökaren aldrig rullar nedåt på sidan innan han/hon går till nästa sida, blir både de högsta procentvärdena visade och de inledande procentvärdena visade lika med samma värde.

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

### 5.0.1 (22 juni 2021)

* Ett problem har korrigerats där vissa specialtecken skulle få plugin-programmet att brytas

### 5.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v4.0 (7 oktober 2019)

* Lagt till `s._ppvFoldsSeen`- och `s._ppvFoldsAvailable`-lösningar

### v3.01 (13 augusti 2018)

* Ett problem har korrigerats för sidor som har flera AppMeasurement-objekt på en sida

### v3.0 (13 april 2018)

* Point release (omkompilerad, mindre kodstorlek)
* Plugin-programmet skapar nu variabler som ska tilldelas till Adobe Analytics-variabler i stället för returvärden
