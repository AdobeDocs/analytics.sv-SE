---
title: getValOnce
description: Förhindra att en Analytics-variabel ställs in på samma värde två gånger i rad.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Adobe plug-in: getValOnce

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

The `getValOnce` plugin-programmet förhindrar att en variabel ställs in på samma värde mer än en gång. Adobe rekommenderar att du använder denna plugin när du vill ta bort dubbletter av förekomster där en besökare uppdaterar en sida eller på annat sätt besöker en viss sida flera gånger. Denna plugin behövs inte om du inte är orolig för förekomstmåttet i Analysis Workspace.

## Installera plugin-programmet med Web SDK eller Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getValOnce
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `getValOnce` funktionen använder följande argument:

* **`vtc`** (required, string): Variabeln som ska kontrolleras och se om den precis har ställts in på ett identiskt värde
* **`cn`** (valfri, sträng): Namnet på den cookie som innehåller värdet som ska kontrolleras. Standardvärdet är `"s_gvo"`
* **`et`** (valfritt, heltal): Cookie-filens utgångsdatum i dagar (eller minuter) beroende på `ep` argument). Standardvärdet är `0`som upphör i slutet av webbläsarsessionen
* **`ep`** (valfri, sträng): Ange bara det här argumentet om `et` -argumentet ställs också in. Ange det här argumentet som `"m"` om du vill ha `et` argument om att förfalla om några minuter i stället för dagar. Standardvärdet är `"d"`, som ställer in `et` argument i dagar.

Om `vtc` argument och cookie-värdesmatchning returnerar den här funktionen en tom sträng. Om `vtc` -argument och cookie-värde matchar inte, funktionen returnerar `vtc` argument som en sträng.

## Exempel

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01

* Ett problem med att skriva cookies har korrigerats.

### 2.0

* Punktrelease (omkompilerad, mindre kodstorlek).

### 1.1

* Lagt till alternativet att välja minuter eller dagar för förfallodatum via `t` parameter.
* Omfånget för `k` variabel som används för att begränsa den till plugin-programmet. Den här ändringen förhindrar eventuell störning av annan kod på sidan.
