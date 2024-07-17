---
title: getGeoCoordinates
description: Spåra en besökares geoLocation.
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Adobe, plugin-program: getGeoCoordinates

{{plug-in}}

Med plugin-programmet `getGeoCoordinates` kan du fånga latitud och longitud för besökarens enheter. Adobe rekommenderar att du använder det här plugin-programmet om du vill hämta geoplatsdata i Analytics-variabler.

## Installera plugin-programmet med Web SDK-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Tags]** till vänster och klicka sedan på den önskade taggegenskapen.
1. Klicka på **[!UICONTROL Extensions]** till vänster och sedan på fliken **[!UICONTROL Catalog]**
1. Leta reda på och installera tillägget **[!UICONTROL Common Web SDK Plugins]**.
1. Klicka på **[!UICONTROL Data Elements]** till vänster och klicka sedan på det önskade dataelementet.
1. Ange det önskade dataelementnamnet med följande konfiguration:
   * Tillägg: Vanliga SDK-plugin-program för webben
   * Dataelement: `getGeoCoordinates`
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
   * Åtgärdstyp: Initiera getGeoCoordinates
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
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getGeoCoordinates` använder inga argument. Det returnerar ett av följande värden:

* `"geo coordinates not available"`: För enheter som inte har geoplatsdata tillgängliga när plugin-programmet körs. Det här värdet är vanligt vid den första besöksträffen, särskilt när besökarna först måste ge sitt samtycke till att spåra sin plats.
* `"error retrieving geo coordinates"`: När plugin-programmet påträffar fel vid försök att hämta enhetens plats
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Där [LATITUDE]/[LONGITUDE] är latituden och longituden

>[!NOTE]
>
>Koordinatvärden avrundas till närmaste fjärde decimal. Värdet `"40.438635333"` avrundas till `"40.4386"` för att begränsa antalet unika värden som ska fångas. Värdena är tillräckligt nära för att identifiera enhetens exakta position inom ca 20 fot.

Detta plugin-program använder en cookie med namnet `"s_ggc"` för att lagra koordinater mellan träffar vid behov.

## Exempel

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## Tidigare versioner

### 2.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.0 (25 maj 2015)

* Ursprunglig version.
