---
title: getValOnce
description: Förhindra att en Analytics-variabel ställs in på samma värde två gånger i rad.
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# Adobe plug-in: getValOnce

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `getValOnce` förhindrar att en variabel ställs in på samma värde mer än en gång. Adobe rekommenderar att du använder denna plugin när du vill ta bort dubbletter av förekomster där en besökare uppdaterar en sida eller på annat sätt besöker en viss sida flera gånger. Denna plugin behövs inte om du inte är orolig för förekomstmåttet i Analysis Workspace.

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
   * Åtgärdstyp: Initiera getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getValOnce` använder följande argument:

* **`vtc`** (required, string): Variabeln som ska kontrolleras och se om den precis har ställts in på ett identiskt värde
* **`cn`** (valfri, sträng): Namnet på den cookie som innehåller värdet som ska kontrolleras. Standardvärdet är `"s_gvo"`
* **`et`** (valfritt, heltal): Cookie-filens förfallodatum i dagar (eller minuter, beroende på  `ep` argumentet). Standardvärdet är `0`, som upphör i slutet av webbläsarsessionen
* **`ep`** (valfri, sträng): Ange bara det här argumentet om  `et` argumentet också anges. Ange det här argumentet som `"m"` om du vill att `et`-argumentet ska upphöra att gälla om några minuter i stället för dagar. Standardvärdet är `"d"`, vilket anger argumentet `et` i dagar.

Om argumentet `vtc` och cookie-värdet matchar returnerar metoden en tom sträng. Om argumentet `vtc` och cookie-värdet inte matchar returnerar metoden argumentet `vtc` som en sträng.

## Exempelanrop

### Exempel 1

Använd det här anropet för att förhindra att samma värde skickas till s.campaign mer än en gång i rad under de kommande 30 dagarna:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

I anropet ovan kommer plugin-programmet först att jämföra värdet som redan finns i s_campaign-cookien med värdet som kommer från den aktuella s.campaign-variabeln.   Om ingen matchning görs kommer plugin-programmet att ställa in s_campaign-cookien som lika med det nya värdet som kommer från s.campaign och sedan returnera det nya värdet.   Jämförelsen kommer att göras de kommande trettio dagarna

### Exempel 3

Använd det här anropet för att förhindra att samma värde anges under hela sessionen:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Den här koden förhindrar att samma värde skickas till s.eVar2 mer än en gång i rad under en användarsession.  m-värdet i stycket (i slutet av anropet) ignoreras eftersom förfallotiden är lika med 0.   I koden lagras också jämförelsevärdet i s_ev2-cookien.

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01

* Ett problem med att skriva cookies har korrigerats.

### 2.0

* Punktrelease (omkompilerad, mindre kodstorlek).

### 1.1

* Alternativet att välja minuter eller dagar för förfallodatum har lagts till via parametern `t`.
* Omfånget för variabeln `k` har korrigerats och används endast för att begränsa den till plugin-programmet. Den här ändringen förhindrar eventuell störning av annan kod på sidan.
