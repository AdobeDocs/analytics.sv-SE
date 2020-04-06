---
title: getGeoCoordinates
description: Spåra en besökares geoLocation.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe plug-in: getGeoCoordinates

>[!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getGeoCoordinates` plugin-programmet kan du fånga latituden och longituden för besökarnas enheter. Adobe rekommenderar att du använder det här plugin-programmet om du vill samla in geoplatsdata i Analytics-variabler.

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
   * Åtgärdstyp: Initiera getGeoCoordinates
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

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden använder inte några argument `getGeoCoordinates` . Det returnerar ett av följande värden:

* `"geo coordinates not available"`: För enheter som inte har geoplatsdata tillgängliga när plugin-programmet körs. Det här värdet är vanligt vid den första besöksträffen, särskilt när besökarna först måste ge sitt samtycke till att spåra sin plats.
* `"error retrieving geo coordinates"`: När plugin-programmet påträffar fel vid försök att hämta enhetens plats
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Där [LATITUDE]/[LONGITUDE] är latitud respektive longitud

>[!NOTE] Koordinatvärden avrundas till närmaste fjärde decimal. Värdet för `"40.438635333"` är till exempel avrundat för `"40.4386"` att begränsa antalet unika värden som ska fångas. Värdena är tillräckligt nära för att identifiera enhetens exakta position inom ca 20 fot.

Detta plugin-program använder en cookie med namnet `"s_ggc"` för att lagra koordinater mellan träffar om det behövs.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.eVar1 = s.getGeoCoordinates();
```

...anger eVar1 som ett av de ovanstående returvärdena beroende på besökarens enhetsstatus

### Exempel 2

Följande kod extraherar latitud och longitud till sina egna variabler, som kallas finalLatitude och finalLongitude, för användning i annan kod/andra program

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

Därifrån kan man se om en besökare är på Frihetsgudinnan:

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## Versionshistorik

### 1.0 (25 maj 2015)

* Ursprunglig version.
