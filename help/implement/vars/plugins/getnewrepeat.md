---
title: getNewRepeat
description: Spåra aktiviteter för nya eller återkommande besökare.
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# Adobe plug-in: getNewRepeat

{{plug-in}}

Med plugin-programmet `getNewRepeat` kan du avgöra om en besökare på webbplatsen är en ny besökare eller en återkommande besökare inom ett visst antal dagar. Adobe rekommenderar att du använder denna plugin om du vill identifiera besökare som&quot;nya&quot; med ett anpassat antal dagar. Denna plugin behövs inte om dimensionerna Ny/Upprepa besökare i Analysis Workspace uppfyller organisationens behov.

## Installera plugin-programmet med Web SDK-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Tags]** till vänster och klicka sedan på den önskade taggegenskapen.
1. Klicka på **[!UICONTROL Extensions]** till vänster och sedan på fliken **[!UICONTROL Catalog]**
1. Leta reda på och installera tillägget **[!UICONTROL Common Web SDK Plugins]**.
1. Klicka på **[!UICONTROL Data Elements]** till vänster och klicka sedan på det önskade dataelementet.
1. Ange det önskade dataelementnamnet med följande konfiguration:
   * Tillägg: Vanliga SDK-plugin-program för webben
   * Dataelement: `getNewRepeat`
1. Ange parametern `daysBeforeReset` till höger.
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
   * Åtgärdstyp: Initiera getNewRepeat
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken [!UICONTROL Configure tracking using custom code] som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurementet

Kopiera och klistra in följande AppMeasurement var som helst i analysfilen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getNewRepeat` använder följande argument:

* **`d`** (heltal, valfritt): Det minsta antal dagar som krävs mellan besök som återställer besökarna till `"New"`. Om argumentet inte är inställt är det som standard 30 dagar.

Den här funktionen returnerar värdet `"New"` om den cookie som angetts av plugin-programmet inte finns eller har gått ut. Värdet `"Repeat"` returneras om den cookie som angetts av plugin-programmet finns och tiden sedan den aktuella träffen och tiden som angetts i cookien är längre än 30 minuter. Den här funktionen returnerar samma värde för ett helt besök.

Detta plugin-program använder en cookie med namnet `"s_nr[LENGTH]"` där `[LENGTH]` är lika med argumentet `d`. Cookien innehåller en Unix-tidsstämpel som representerar den aktuella tiden och besökarens aktuella status (`"New"` eller `"Repeat"`).

## Exempel

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Tidigare versioner

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (30 september 2019)

* Omstrukturering av JavaScript-logik för att minska plugin-programmets storlek

### 2.0 (16 april 2018)

* Kompilerad med mindre kodstorlek
* Det gick inte att namnge cookien för att lagra besöksinformationen. Plugin-programmet namnger nu cookien dynamiskt baserat på det värde som skickades till argumentet `d`.
