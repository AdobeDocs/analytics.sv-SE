---
title: getVisitNum
description: Spåra besökarens aktuella besöksnummer.
feature: Appmeasurement Implementation
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---

# Adobe plug-in: getVisitNum

{{plug-in}}

Plugin-programmet `getVisitNum` returnerar besöksnumret för alla besökare som kommer till webbplatsen inom det önskade antalet dagar. Analysis Workspace erbjuder en dimension av typen Besök nummer som ger liknande funktionalitet. Adobe rekommenderar att du använder denna plugin om du vill ha mer kontroll över hur besöksnumret ökar. Denna plugin behövs inte om den inbyggda dimensionen &#39;Besök nummer&#39; i Analysis Workspace är tillräcklig för dina rapporteringsbehov.

## Installera plugin-programmet med Web SDK-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Tags]** till vänster och klicka sedan på den önskade taggegenskapen.
1. Klicka på **[!UICONTROL Extensions]** till vänster och sedan på fliken **[!UICONTROL Catalog]**
1. Leta reda på och installera tillägget **[!UICONTROL Common Web SDK Plugins]**.
1. Klicka på **[!UICONTROL Data Elements]** till vänster och klicka sedan på det önskade dataelementet.
1. Ange det önskade dataelementnamnet med följande konfiguration:
   * Tillägg: Vanliga SDK-plugin-program för webben
   * Dataelement: `getVisitNum`
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
   * Åtgärdstyp: Initiera getVisitNum
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getVisitNum` använder följande argument:

* **`rp`** (valfritt, heltal ELLER sträng): Antalet dagar innan besöksnummerräknaren återställs.  Standardvärdet är `365` när det inte anges.
   * När det här argumentet är `"w"` återställs räknaren i slutet av veckan (den här lördagen klockan 11:59)
   * När argumentet är `"m"` återställs räknaren i slutet av månaden (den sista dagen i den här månaden)
   * När det här argumentet är `"y"` återställs räknaren i slutet av året (31 december)
* **`erp`** (valfritt, booleskt): När argumentet `rp` är ett tal avgör det här argumentet om giltigheten för besöksnumret ska förlängas. Om värdet är `true` återställs besöksnummerräknaren vid efterföljande träffar på din webbplats. Om värdet är `false` utökas inte efterföljande träffar på din webbplats när besöksnummerräknaren återställs. Standardvärdet är `true`. Det här argumentet är inte giltigt när argumentet `rp` är en sträng.

Besöksnummerökningen när besökaren återvänder till er webbplats efter 30 minuters inaktivitet. Om den här funktionen anropas returneras ett heltal som representerar besökarens aktuella besöksnummer.

Detta plugin-program ställer in en cookie från första part med namnet `"s_vnc[LENGTH]"` där `[LENGTH]` är värdet som skickas till argumentet `rp`. Till exempel `"s_vncw"`, `"s_vncm"` eller `"s_vnc365"`. Värdet för cookien är en kombination av en Unix-tidsstämpel som representerar när besöksräknaren återställs, till exempel slutet av veckan, slutet av månaden eller efter 365 dagars inaktivitet. Den innehåller även det aktuella besöksnumret. Detta plugin-program ställer in en annan cookie med namnet `"s_ivc"` som är inställd på `true` och upphör att gälla efter 30 minuters inaktivitet.

## Exempel

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## Tidigare versioner

### 4.2 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 4.11 (30 september 2019)

* Ett problem har korrigerats där argumentet `erp` uttryckligen angavs till `false`.

### 4.1 (21 maj 2018)

* Plugin-programmet `endOfDatePeriod` har uppdaterats till v1.1.

### 4.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Tog bort cookie-argument eftersom plugin-programmet nu dynamiskt genererar cookies baserat på argumentet `rp`)

### 3.0 (5 juni 2016)

* fullständig översyn
* Kombinera alla tidigare lösningar som finns i olika versioner av plugin-programmet `getVisitNum`.
