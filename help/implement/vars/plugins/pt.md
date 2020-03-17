---
title: pt
description: Kör en funktion i en lista med variabler.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: pt

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin- `pt` programmet kör en funktion eller metod i en lista med Analytics-variabler. Du kan till exempel selektivt köra metoden på flera variabler utan att anropa metoden manuellt varje gång. `clearVars` Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

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
   * Åtgärdstyp: Initiera pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `pt`

* **`l`** (required, string): En lista med variabler som funktionen i `cf` argumentet kan köras mot.
* **`de`** (valfri, sträng): Avgränsaren som avgränsar variabellistan i `l` argumentet. Standardvärdet är ett komma (`,`).
* **`cf`** (required, string): Namnet på callback-funktionen i AppMeasurement-objektet som ska anropas mot alla variabler som finns i `l` argumentet.
* **`fa`** (valfri, sträng): Om funktionen i `cf` argumentet anropar ytterligare argument när den körs, ska du inkludera dem här. Standardvärdet är `undefined`.

Om den här metoden anropas returneras ett värde om återanropsfunktionen (i `cf` argumentet) returnerar ett värde.

## Exempelanrop

### Exempel 1

Följande kod ingår i plugin-programmet getQueryParam.  Den kör hjälpfunktionen getParameterValue mot vart och ett av de nyckel/värde-par som finns i URL:ens frågesträng (fullQueryString).  För att extrahera varje nyckelvärdepar måste fullQueryString avgränsas och delas upp med ett et-tecken (&amp;). ParameternKey refererar till frågesträngsparametern som plugin-programmet specifikt försöker extrahera från frågesträngen

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

Ovanstående rad är en genväg för att köra kod som liknar följande:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Versionshistorik

### 2.01 (24 september 2019)

* Mindre kodändringar för att minska den totala storleken

### 2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Stöd för både H-kod och AppMeasurement har lagts till.

### 1.0 (23 september 2013)

* Ursprunglig version.
