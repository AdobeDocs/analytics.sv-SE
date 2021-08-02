---
title: getNewRepeat
description: Spåra aktiviteter för nya eller återkommande besökare.
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
source-git-commit: 13060d08c8ffff01d8dae379e090c53e61fa6476
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Adobe plug-in: getNewRepeat

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getNewRepeat` kan du avgöra om en besökare på webbplatsen är en ny besökare eller en återkommande besökare inom ett visst antal dagar. Adobe rekommenderar att du använder denna plugin om du vill identifiera besökare som&quot;nya&quot; med ett anpassat antal dagar. Denna plugin behövs inte om dimensionerna Ny/Upprepa besökare i Analysis Workspace uppfyller organisationens behov.

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
   * Åtgärdstyp: Initiera getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getNewRepeat` använder följande argument:

* **`d`** (heltal, valfritt): Minsta antal dagar mellan besöken som återställer besökarna till  `"New"`. Om argumentet inte är inställt är det som standard 30 dagar.

Den här metoden returnerar värdet `"New"` om den cookie som angetts av plugin-programmet inte finns eller har upphört att gälla. Värdet `"Repeat"` returneras om den cookie som angetts av plugin-programmet finns och tiden sedan den aktuella träffen och tiden som angetts i cookien är längre än 30 minuter. Den här metoden returnerar samma värde för ett helt besök.

Detta plugin-program använder en cookie med namnet `"s_nr[LENGTH]"` där `[LENGTH]` är lika med argumentet `d`. Cookien innehåller en Unix-tidsstämpel som representerar den aktuella tiden och besökarens aktuella status (`"New"` eller `"Repeat"`).

## Exempelanrop

### Exempel 1

Följande kod ställer in `eVar1` på värdet `"New"` för nya besökare och fortsätter att ställa in `eVar1` på värdet `"New"` (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1 = getNewRepeat();
```

### Exempel 3

Om besökaren kommer tillbaka till webbplatsen när som helst från 31 minuter till 30 dagar sedan den senaste gången `getNewRepeat()` anropades, sätter följande kod `eVar1` till värdet `"Repeat"` och fortsätter att ställa in `eVar1` till värdet `"Repeat"` (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1 = getNewRepeat();
```

### Exempel 2

Om besökaren inte har varit på webbplatsen på minst 30 dagar sedan den senaste gången `getNewRepeat()` anropades, sätter följande kod `eVar1` till värdet `"New"` och fortsätter att ställa in `eVar1` till värdet `"New"` (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1 = getNewRepeat();
```

### Exempel 4

Om besökaren kommer tillbaka till webbplatsen 31 minuter till 365 dagar (dvs. 1 år) sedan den senaste gången `getNewRepeat()` anropades, sätter följande kod `eVar1` till värdet `"Repeat"` och fortsätter att ställa in `eVar1` till värdet `"Repeat"` (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1 = getNewRepeat(365);
```

### Exempel 5

Om besökaren inte har varit på webbplatsen på minst 365 dagar (dvs. 1 år) sedan den senaste gången `getNewRepeat()` anropades, sätter följande kod `eVar1` till värdet `"New"` och fortsätter att ställa in `eVar1` till värdet `"New"` (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1 = getNewRepeat(365);
```

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (30 september 2019)

* Ordna om JavaScript-logiken för att minska plugin-programmets storlek

### 2.0 (16 april 2018)

* Kompilerad med mindre kodstorlek
* Det gick inte att namnge cookien för att lagra besöksinformationen. Plugin-programmet namnger nu cookien dynamiskt baserat på det värde som skickas till `d`-argumentet.
