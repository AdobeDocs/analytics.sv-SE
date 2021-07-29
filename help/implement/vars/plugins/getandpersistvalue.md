---
title: getAndPersistValue
description: Lagra ett värde som kan hämtas senare när som helst.
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# Adobe plug-in: getAndPersistValue

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getAndPersistValue` kan du lagra ett värde i en cookie som kan hämtas senare under ett besök. Den har en liknande roll som [!UICONTROL Storage duration]-funktionen med taggar i Adobe Experience Platform. Adobe rekommenderar att du använder det här plugin-programmet om du automatiskt vill behålla en Analytics-variabel på samma värde i efterföljande träffar efter att variabeln har angetts. Detta plugin-program är inte nödvändigt om funktionen [!UICONTROL Storage duration] i Adobe Experience Platform är tillräcklig. Du behöver inte heller använda denna plugin om du inte behöver ställa in och behålla variabler till samma värde i efterföljande träffar. Den inbyggda eVars-beständigheten kräver inte att denna plugin används eftersom dessa variabler finns kvar på Adobe.

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
   * Åtgärdstyp: Initiera getAndPersistValue
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getAndPersist` använder följande argument:

* **`vtp`** (obligatoriskt): Värdet som ska behållas från sida till sida
* **`cn`** (valfritt): Namnet på den cookie som värdet ska lagras i. Om det här argumentet inte anges får cookien namnet `"s_gapv"`
* **`ex`** (valfritt): Antalet dagar innan cookien förfaller. Om argumentet är `0` eller inte är inställt upphör cookien att gälla när besöket är slut (30 minuters inaktivitet).

Om variabeln i `vtp`-argumentet är inställd ställer plugin-programmet in cookien och returnerar sedan cookie-värdet. Om variabeln i `vtp`-argumentet inte är inställd returnerar plugin-programmet bara cookie-värdet.

## Exempel

### Exempel 1

I följande kod ställs eVar21 in på samma värde som &quot;hello&quot;.  Koden ställer sedan in ev21gapv-cookien, som upphör att gälla om 28 dagar, som är lika med värdet för eVar21 (dvs. &quot;hej&quot;).  Koden ställer sedan in (re) eVar21 som lika med värdet för ev21gapv-cookien.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 3

Anta att eVar21 inte har ställts in på den aktuella sidan än, men har ställts in på &quot;hello&quot; på en tidigare sida under de senaste 28 dagarna.   Följande kod ställer bara in eVar21 som är lika med värdet för ev21gapv-cookien (d.v.s. &quot;hej&quot;).  Ev21gapv-cookien återställs inte eftersom eVar21 inte hade angetts på den aktuella sidan innan funktionen anropades.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 2

Anta att eVar21 inte har ställts in på den aktuella sidan än, men har ställts in på &quot;hello&quot; på en tidigare sida under de senaste 28 dagarna.  Följande kod ställer bara in prop35 som är lika med värdet för ev21gapv-cookien (d.v.s. &quot;hej&quot;).  eVar21 kommer inte att anges.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 4

I följande kod ställs eVar21 in på samma värde som &quot;howdy&quot;.  Koden kommer sedan att ställa in (eller återställa) den v21gapv-cookien, som upphör att gälla om 28 dagar, som är lika med värdet för eVar21 (dvs. &quot;hur&quot;).  Koden ställer sedan in prop35 som är lika med värdet för ev21gapv-cookien (dvs. &quot;hur&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 5

Anta att s.eVar21 inte har angetts på några sidor under de senaste 28 dagarna.  Följande kod ställer in s.eVar21 till ingenting eftersom v21gapv-cookien skulle ha gått ut 28 dagar efter att den senast ställdes in.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 6

Följande kod ställer in eVar30 till &quot;shopping&quot;.  Sedan ställs s_gapv-cookien in, som upphör att gälla i slutet av webbläsarsessionen, som är lika med värdet för s.eVar30 (dvs. &quot;handla&quot;).  Sedan ställs s.eVar30 in som lika med värdet för s_gapv-cookien (d.v.s. anropet getAndPersistValue returnerar värdet för s_gapv-cookien, som i det här fallet är &quot;handla&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Om s.eVar30 inte är inställt på ett explicit värde på eventuella ytterligare sidor som visas under sessionen, men är inställt (in doPlugins) via följande kod..

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 anges som lika med &quot;handla&quot; (dvs. det beständiga värdet för s_gapv-cookien)

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.0 (16 april 2018)

* Point release (mindre kodstorlek)
* Om du anger 0 i `ex`-argumentet upphör nu att gälla efter 30 minuters inaktivitet i stället för att upphöra i slutet av webbläsarsessionen.

### 1.0 (18 januari 2016)

* Ursprunglig version.
