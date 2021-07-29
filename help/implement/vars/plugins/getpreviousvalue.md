---
title: getPreviousValue
description: Hämta det sista värdet som skickades till en variabel.
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# Adobe plug-in: getPreviousValue

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getPreviousValue` kan du ställa in en variabel på ett värde som angetts vid en tidigare träff. Detta plugin-program behövs inte om implementeringen innehåller alla önskade värden i den aktuella träffen.

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getPreviousValue
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getPreviousValue` använder följande argument:

* **`v`** (sträng, obligatoriskt): Variabeln som har värdet som du vill skicka till nästa bildförfrågan. En vanlig variabel som används är `s.pageName` för att hämta föregående sidvärde.
* **`c`** (sträng, valfritt): Namnet på den cookie som lagrar värdet.  Om argumentet inte är inställt är det som standard `"s_gpv"`.

När du anropar den här metoden returnerar den strängvärdet som finns i cookien. Plugin-programmet återställer sedan förfallotiden för cookie och tilldelar det variabelvärdet från `v`-argumentet. Kakan går ut efter 30 minuters inaktivitet.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Först anges s.prop7 som lika med värdet som skickades till s.pageName i föregående bildbegäran (dvs. värdet som lagrats i cookien &quot;gpv_Page&quot;)
* Koden återställer sedan cookien &quot;gpv_Page&quot;, vilket gör den lika med det aktuella värdet för s.pageName
* Om s.pageName inte anges när den här koden körs återställer koden förfallotiden för cookie-filens aktuella värde

### Exempel 2

I följande kod anges s.prop7 som lika med det senaste värdet som skickas till s.pageName, men bara om event1 också finns i s.events, som bestämts via plugin-programmet inList, när anropet görs.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exempel 2

Följande kod ställer in s.prop7 på det senaste värdet som skickas till s.pageName, men bara om s.pageName är inställt på sidan samtidigt.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exempel 4

Följande kod ställer in s.eVar10 som lika med värdet som skickades till s.eVar1 i föregående bildbegäran.   Det tidigare eVar1-värdet skulle ha funnits med i s_gpv-cookien.  Koden ställer sedan in cookien &quot;s_gpv&quot; som är lika med det aktuella värdet för s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Osannolikt fel

Om variabeln som är associerad med argumentet v är inställd på ett nytt värde och plugin-programmet getPreviousValue körs MEN ett anrop från en Analytics-server skickas INTE samtidigt, kommer det nya argumentvärdet v fortfarande att betraktas som&quot;föregående värde&quot; nästa gång plugin-programmet körs.
Anta till exempel att följande kod körs på den första sidan av besöket:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Den här koden skulle skapa ett serveranrop där pageName-argumentet är lika med&quot;home&quot; och p7-argumentet (prop7) inte är inställt.  Anropet till s.getPreviousValue skulle emellertid lagra värdet för s.pageName (dvs. &quot;home&quot;) i den cookie som anges i anropet (dvs. cookien &quot;gpv_Page&quot;).
Anta nu att följande kod körs omedelbart därefter på samma sida (av någon anledning):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Eftersom funktionen s.t() inte körs i det här kodblocket skapas ingen annan bildbegäran.  När funktionskoden s.getPreviousValue() körs den här gången ställs s.prop7 in på samma som det tidigare värdet för s.pageName (d.v.s. &quot;home&quot;) och sedan kommer att lagra det nya värdet för s.pageName (dvs. &quot;lycklig value&quot;) i cookien &quot;gpv_Page&quot;.
Anta att besökaren navigerar till en annan sida och att följande kod körs på den här sidan:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

När s.t()-anropsfunktionen körs skapas en bildbegäran där s.pageName=&quot;page 2&quot; och s.prop7 är lika med&quot;Happy value&quot;, som var värdet för s.pageName när det senaste anropet till getPreviousValue ägde rum.   s.prop7-värdet för home fanns aldrig med i någon verklig bildbegäran trots att home var det första värdet som skickades till s.pageName.

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### v2.0 (7 oktober 2019)

* Punktversion (fullständig logikomskrivning).
