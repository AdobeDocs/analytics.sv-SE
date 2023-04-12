---
title: pt
description: Kör en funktion i en lista med variabler.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Adobe plug-in: pt

{{plug-in}}

The `pt` plugin-programmet kör en funktion eller metod i en lista med Analytics-variabler. Du kan till exempel selektivt köra [`clearVars`](../functions/clearvars.md) på flera variabler utan att funktionen anropas manuellt varje gång. Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera pt
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `pt` funktionen använder följande argument:

* **`l`** (required, string): En lista med variabler som funktionen i `cf` -argument kan köras mot.
* **`de`** (valfri, sträng): Avgränsaren som avgränsar variabellistan i `l` argument. Standardvärdet är ett komma (`,`).
* **`cf`** (required, string): Namnet på återanropsfunktionen i AppMeasurement-objektet som ska anropas mot var och en av variablerna i `l` argument.
* **`fa`** (valfri, sträng): Om funktionen i `cf` argument kräver ytterligare argument när det körs, ta med dem här. Standardvärdet är `undefined`.

Anrop till den här funktionen returnerar ett värde om callback-funktionen (i `cf` argument) returnerar ett värde.

## Exempelanrop

### Exempel 1

Följande kod ingår i plugin-programmet getQueryParam.  Den kör hjälpfunktionen getParameterValue mot vart och ett av de nyckel/värde-par som finns i URL:ens frågesträng (fullQueryString).  För att extrahera varje nyckelvärdepar måste fullQueryString avgränsas och delas upp med ett et-tecken (&amp;). ParameternKey refererar till frågesträngsparametern som plugin-programmet specifikt försöker extrahera från frågesträngen

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

Ovanstående rad är en genväg för att köra kod som liknar följande:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01 (24 september 2019)

* Mindre kodändringar för att minska den totala storleken

### 2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Stöd för både H-kod och AppMeasurement har lagts till.

### 1.0 (23 september 2013)

* Ursprunglig version.
