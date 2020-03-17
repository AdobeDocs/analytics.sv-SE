---
title: getPreviousValue
description: Hämta det sista värdet som skickades till en variabel.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getPreviousValue

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getPreviousValue` plugin-programmet kan du ställa in en variabel på ett värde som ställts in vid en tidigare träff. Detta plugin-program behövs inte om implementeringen innehåller alla önskade värden i den aktuella träffen.

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
   * Åtgärdstyp: Initiera getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getPreviousValue`

* **`v`** (sträng, obligatoriskt): Variabeln som har värdet som du vill skicka till nästa bildförfrågan. En vanlig variabel som används är `s.pageName` att hämta föregående sidvärde.
* **`c`** (sträng, valfritt): Namnet på den cookie som lagrar värdet.  Om argumentet inte är inställt blir det som standard `"s_gpv"`.

När du anropar den här metoden returnerar den strängvärdet som finns i cookien. Plugin-programmet återställer sedan förfallotiden för cookie och tilldelar det variabelvärdet från `v` argumentet. Kakan går ut efter 30 minuters inaktivitet.

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

### Exempel 3

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

### v2.0 (7 oktober 2019)

* Punktversion (fullständig logikomskrivning).
