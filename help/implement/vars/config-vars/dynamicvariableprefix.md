---
title: dynamicVariablePrefix
description: Gör att du kan anpassa strängen som identifierar dynamiska variabler.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# dynamicVariablePrefix

Dynamiska variabler är ett koncept med vilket du kan kopiera värden från en variabel till en annan. De är användbara för långa variabelvärden eftersom de hjälper till att korta URL-längden för en bildförfrågan. Se [Dynamiska variabler](../page-vars/dynamic-variables.md) för mer information om detta koncept.

Som standard använder dynamiska variabler prefixet `D=`. The `dynamicVariablePrefix` kan du anpassa strängen som identifierar dynamiska variabler. Den är skiftlägeskänslig.

## Dynamiskt variabelprefix med taggar i Adobe Experience Platform

Dynamiskt variabelprefix är ett fält under [!UICONTROL Global Variables] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Global Variables] dragspelspanel, som visar [!UICONTROL Dynamic Variable Prefix] fält.

Det här fältet innehåller `D=` som standard. Du kan ändra värdet om du vill använda ett annat dynamiskt variabelprefix. Du kan använda vilket värde du vill, förutsatt att det matchar teckenkodningen på webbplatsen.

## s.dynamicVariablePrefix i AppMeasurement och anpassad kodredigerare

The `s.dynamicVariablePrefix` variabeln är en sträng som kan innehålla vilken teckensekvens som helst. Om variabeln inte är definierad använder AppMeasurement strängen `D=` som standard.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
