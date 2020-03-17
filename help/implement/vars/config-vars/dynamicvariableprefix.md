---
title: dynamicVariablePrefix
description: Gör att du kan anpassa strängen som identifierar dynamiska variabler.
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

Dynamiska variabler är ett koncept med vilket du kan kopiera värden från en variabel till en annan. De är användbara för långa variabelvärden eftersom de hjälper till att korta URL-längden för en bildförfrågan. Mer information om detta koncept finns i [Dynamiska variabler](../page-vars/dynamic-variables.md) .

Som standard använder dynamiska variabler prefixet `D=`. Med `dynamicVariablePrefix` variabeln kan du anpassa strängen som identifierar dynamiska variabler. Den är skiftlägeskänslig.

## Dynamiskt variabelprefix i Adobe Experience Platform Launch

Dynamiskt variabelprefix är ett fält under [!UICONTROL Global Variables] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Global Variables] [!UICONTROL Dynamic Variable Prefix] fältet.

Det här fältet innehåller `D=` som standard. Du kan ändra värdet om du vill använda ett annat dynamiskt variabelprefix. Du kan använda vilket värde du vill, förutsatt att det matchar teckenkodningen på webbplatsen.

## s.dynamicVariablePrefix i AppMeasurement and Launch custom code editor

Variabeln `s.dynamicVariablePrefix` är en sträng som kan innehålla vilken teckensekvens som helst. Om variabeln inte definieras används strängen `D=` som standard.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
