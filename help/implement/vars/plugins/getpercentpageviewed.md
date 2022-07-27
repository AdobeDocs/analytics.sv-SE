---
title: getPercentPageViewed
description: Hämta den procentandel av sidan som besökaren visade.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Adobe plug-in: getPercentPageViewed

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

The `getPercentPageViewed` plugin-programmet mäter besökarens rullningsaktivitet för att se hur mycket av en sida de visar innan de går vidare till en annan sida. Denna plugin behövs inte om sidorna är små i höjdled eller inte vill mäta rullningsaktiviteten.

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
    * Action Type: Initialize getPercentPageViewed
1. Save and publish the changes to the rule.-->

## Installera plugin-programmet med en anpassad kodredigerare

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `getPercentPageViewed` funktionen använder följande argument:

* **`pid`** (valfri, sträng): En sidbaserad identifierare som du kan korrelera med procentsatserna som anges i plugin-programmets mått.  Standardvärdet är `pageName` variabel.
* **`ch`** (valfritt, boolesk): Ange detta till `false` (eller `0`) om du inte vill att plugin-programmet ska ta hänsyn till ändringar som gjorts i sidstorleken efter den första inläsningen. Om det utelämnas används det här argumentet som standard `true`. Adobe rekommenderar att detta argument utelämnas i de flesta fall.

När funktionen anropas returneras ingenting; i stället anges följande variabler:

* `s._ppvPreviousPage`: Namnet på föregående sida som visades. Slutliga rullningsmått för den aktuella sidan är inte tillgängliga förrän en ny sida har lästs in.
* `s._ppvHighestPercentViewed`: Den högsta procentandel av föregående sida som besökaren visade (höjdvis). Den längst punkten som besökaren rullade ned till på föregående sida. Om hela sidan är synlig när den läses in första gången, är det här värdet `100`.
* `s._ppvInitialPercentViewed`: Den procentandel av föregående sida som var synlig när föregående sida först lästes in. Om hela sidan är synlig när den läses in första gången, är det här värdet `100`.
* `s._ppvHighestPixelsSeen`: Det högsta antalet pixlar som visas (höjdvis) när besökaren rullade nedåt på föregående sida.
* `s._ppvFoldsSeen`: Det högsta antalet sidvikningar som nås när besökaren rullade nedåt på föregående sida. Den här variabeln innehåller &quot;top-of-page&quot;-vikningen. Om hela sidan är synlig när den läses in första gången, är det här värdet `1`.
* `s._ppvFoldsAvailable`: Det totala antalet&quot;sidvikningar&quot; som är tillgängliga för rullning nedåt på föregående sida. Om hela sidan är synlig när den läses in första gången, är det här värdet `1`.

Tilldela en eller flera av dessa variabler till eVars för att visa dimensionsdata i rapporter.

Denna plugin skapar en cookie från första part som kallas `s_ppv` som innehåller ovanstående värden. Den förfaller i slutet av webbläsarsessionen.

## Exempel

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed, the intial percent, the number of folds viewed, and total number of folds of the previous page
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed + " | foldsSeen=" + _ppvFoldsSeen + " | foldsAvailable=" + _ppvFoldsAvailable;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed and the initial percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed;
}
```

## Versionshistorik

### 5.0.1 (22 juni 2021)

* Ett problem har korrigerats där vissa specialtecken skulle få plugin-programmet att brytas

### 5.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v4.0 (7 oktober 2019)

* Tillagd `s._ppvFoldsSeen` och `s._ppvFoldsAvailable` lösningar

### v3.01 (13 augusti 2018)

* Ett problem har korrigerats för sidor som har flera AppMeasurement-objekt på en sida

### v3.0 (13 april 2018)

* Point release (omkompilerad, mindre kodstorlek)
* Plugin-programmet skapar nu variabler som ska tilldelas till Adobe Analytics-variabler i stället för returvärden
