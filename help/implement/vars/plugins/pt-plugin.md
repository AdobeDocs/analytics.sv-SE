---
title: pt
description: Kör en funktion i en lista med variabler.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Adobe plug-in: pt

{{plug-in}}

Plugin-programmet `pt` kör en funktion eller metod i en lista med Analytics-variabler. Du kan till exempel selektivt köra funktionen [`clearVars`](../functions/clearvars.md) på flera variabler utan att manuellt anropa funktionen varje gång. Flera andra plugin-program är beroende av att den här koden körs korrekt. Detta plugin-program är inte nödvändigt om du inte behöver köra en specifik funktion på mer än en Analytics-variabel åt gången, eller om du inte använder några beroende plugin-program.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

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
   * Åtgärdstyp: Initiera pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `pt` använder följande argument:

* **`l`** (obligatoriskt, sträng): En lista med variabler som funktionen i argumentet `cf` kan köras mot.
* **`de`** (valfri, sträng): Avgränsaren som avgränsar listan med variabler i argumentet `l`. Standardvärdet är ett komma (`,`).
* **`cf`** (required, string): Namnet på callback-funktionen som finns i AppMeasurementet som ska anropas mot alla variabler som finns i `l` -argumentet.
* **`fa`** (valfri, sträng): Om funktionen i argumentet `cf` anropar ytterligare argument när den körs, ska du inkludera dem här. Standardvärdet är `undefined`.

Om funktionen anropas returneras ett värde om återanropsfunktionen (i argumentet `cf`) returnerar ett värde.

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

## Tidigare versioner

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.01 (24 september 2019)

* Mindre kodändringar för att minska den totala storleken

### 2.0 (17 april 2018)

* Punktrelease (omkompilerad, mindre kodstorlek).
* Stöd för både H-kod och AppMeasurement har lagts till.

### 1.0 (23 september 2013)

* Ursprunglig version.
