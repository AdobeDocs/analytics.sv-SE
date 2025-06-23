---
title: getPreviousValue
description: Hämta det sista värdet som skickades till en variabel.
feature: Appmeasurement Implementation
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---

# Adobe plug-in: getPreviousValue

{{plug-in}}

Med plugin-programmet `getPreviousValue` kan du ange en variabel till ett värde som angetts vid en tidigare träff. Detta plugin-program behövs inte om implementeringen innehåller alla önskade värden i den aktuella träffen.

## Installera plugin-programmet med Web SDK-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Tags]** till vänster och klicka sedan på den önskade taggegenskapen.
1. Klicka på **[!UICONTROL Extensions]** till vänster och sedan på fliken **[!UICONTROL Catalog]**
1. Leta reda på och installera tillägget **[!UICONTROL Common Web SDK Plugins]**.
1. Klicka på **[!UICONTROL Data Elements]** till vänster och klicka sedan på det önskade dataelementet.
1. Ange det önskade dataelementnamnet med följande konfiguration:
   * Tillägg: Vanliga SDK-plugin-program för webben
   * Dataelement: `getPreviousValue`
1. Ange önskade parametrar till höger.
1. Spara och publicera ändringarna i dataelementet.

## Installera plugin-programmet manuellt för att implementera Web SDK

Denna plugin stöds ännu inte för användning i en manuell implementering av Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Inget
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för gemensam analys
   * Åtgärdstyp: Initiera getPreviousValue
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken [!UICONTROL Configure tracking using custom code] som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getPreviousValue` använder följande argument:

* **`v`** (sträng, krävs): Variabeln som har värdet som du vill skicka till nästa bildbegäran. En vanlig variabel som används är `s.pageName` för att hämta föregående sidvärde.
* **`c`** (sträng, valfritt): Namnet på den cookie som lagrar värdet.  Om det här argumentet inte anges är standardvärdet `"s_gpv"`.

När du anropar den här funktionen returneras strängvärdet som finns i cookien. Plugin-programmet återställer sedan förfallotiden för cookie och tilldelar det variabelvärdet från argumentet `v`. Kakan går ut efter 30 minuters inaktivitet.

## Exempel

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## Osannolikt fel

Om variabeln som är associerad med argumentet `v` är inställd på ett nytt värde och plugin-programmet `getPreviousValue` körs MEN ett serveranrop från Analytics INTE skickas samtidigt, betraktas det nya argumentvärdet `v` fortfarande som&quot;föregående värde&quot; nästa gång plugin-programmet körs.
Anta till exempel att följande kod körs på den första sidan av besöket:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Den här koden skapar ett serveranrop där `pageName` är Home och prop7 inte är inställt.  Anropet till `getPreviousValue` lagrar dock värdet för `pageName` i `gpv_Page`-cookien. Anta att följande kod körs omedelbart därefter på samma sida:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Eftersom funktionen `t()` inte körs i det här kodblocket skickas ingen annan bildbegäran.  När funktionskoden `getPreviousValue` körs den här gången ställs `prop7` in på det tidigare värdet `pageName` (&quot;Hem&quot;) och sedan sparas det nya värdet `pageName` (&quot;Nytt värde&quot;) i cookien `gpv_Page`. Anta sedan att besökaren navigerar till en annan sida och att följande kod körs på den här sidan:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

När funktionen `t()` körs skapas en bildbegäran där `pageName` är &quot;Sida 2&quot; och `prop7` är &quot;Nytt värde&quot;, vilket var värdet `pageName` när det senaste anropet till `getPreviousValue` ägde rum. Värdet `prop7` för `"Home"` fanns aldrig i en bildbegäran, även om Home var det första värdet som skickades till `pageName`.

## Tidigare versioner

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v2.0 (7 oktober 2019)

* Punktversion (fullständig logikomskrivning).
