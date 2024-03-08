---
title: getPercentPageViewed
description: Hämta den procentandel av sidan som besökaren visade.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: d53a2aba80455c2d807bc47e579cad4483c99c3b
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 0%

---

# Adobe plug-in: getPercentPageViewed

{{plug-in}}

The `getPercentPageViewed` plugin-programmet mäter besökarens rullningsaktivitet för att se hur mycket av en sida de visar innan de går vidare till en annan sida. Denna plugin behövs inte om sidorna är små i höjdled eller inte vill mäta rullningsaktiviteten.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Inget
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för gemensam analys
   * Åtgärdstyp: Initiera getPercentPageViewed
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurementet

Kopiera och klistra in följande AppMeasurement var som helst i analysfilen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `getPercentPageViewed` funktionen använder följande argument:

* **`pid`** (valfri sträng): En variabel eller ett värde som är lika med den aktuella sidan. Standardvärdet är Analytics-AppMeasurementet `pageName` variabeln OR the current URL if the AppMeasurement pageName variable is not set.
* **`ch`** (valfritt, booleskt): Ange detta till `false` (eller `0`) om du inte vill att plugin-programmet ska ta hänsyn till ändringar som gjorts i sidstorleken efter den första inläsningen. Om det utelämnas används det här argumentet som standard `true`. Adobe rekommenderar att detta argument utelämnas i de flesta fall.

Om du anropar den här funktionen returneras ingenting. I stället anges följande variabler:

* `window._ppvPreviousPage`: Namnet på den föregående sida som visas. Slutliga rullningsmått för den aktuella sidan är inte tillgängliga förrän en ny sida har lästs in.
* `window._ppvInitialPercentViewed`: Den procentandel av föregående sida som var synlig när föregående sida först lästes in. Om hela sidan är synlig när den läses in första gången, är det här värdet `100`.
* `window._ppvHighestPercentViewed`: Den högsta procentandel av föregående sida som besökaren visade (höjdvis). Den längst punkten som besökaren rullade ned till på föregående sida. Om hela sidan är synlig när den läses in första gången, är det här värdet `100`.
* `window._ppvFinalPercentViewed`: Den procentandel av föregående sida som var synlig vid den punkt besökaren flyttade till den aktuella sidan. Värdet är lika med eller större än den ursprungliga procentandelen som visas och är lika med eller mindre än den högsta procentsidan som visas.
* `window._ppvHighestPixelsSeen`: Det högsta antalet totala pixlar som visas (höjdvis) när besökaren rullade nedåt på föregående sida.
* `window._ppvFoldsAvailable`: Det totala antalet&quot;sidvikningar&quot; som kan rullas nedåt på föregående sida. Om hela sidan är synlig när den läses in första gången, är det här värdet `1`.
* `window._ppvFoldsSeen`: Det högsta antalet sidvikningar som nås när besökaren rullade nedåt på föregående sida. Den här variabeln innehåller &quot;top-of-page&quot;-vikningen. Om hela sidan är synlig när den läses in första gången, är det här värdet `1`.

Tilldela en eller flera av dessa variabler till eVars för att visa dimensionsdata i rapporter.

Detta plugin-program skapar tre cookies från första part som upphör i slutet av en webbläsarsession:

* `s_ppv`: Lagrar alla värden som visas genom att funktionen anropas
* `s_tp`: Sparar den totala pixelhöjden för föregående sida
* `s_ips`: Sparar den inledande procentandelen rullad från föregående sida

## Exempel

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## Tidigare versioner

### 5.1 (8 december 2022)

* Lagt till `_finalPercentViewed` lösning

### 5.0.1 (22 juni 2021)

* Ett problem har korrigerats där vissa specialtecken skulle få plugin-programmet att brytas

### 5.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v4.0 (7 oktober 2019)

* Tillagd `s._ppvFoldsSeen` och `s._ppvFoldsAvailable` lösningar

### v3.01 (13 augusti 2018)

* Ett problem har korrigerats för sidor som har flera AppMeasurement på en sida

### v3.0 (13 april 2018)

* Point release (omkompilerad, mindre kodstorlek)
* Plugin-programmet skapar nu variabler som ska tilldelas till Adobe Analytics-variabler i stället för returvärden
