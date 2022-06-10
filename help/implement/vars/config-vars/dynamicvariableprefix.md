---
title: dynamicVariablePrefix
description: Gör att du kan anpassa strängen som identifierar dynamiska variabler.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# dynamicVariablePrefix

Dynamiska variabler är ett koncept med vilket du kan kopiera värden från en variabel till en annan. De är användbara för långa variabelvärden eftersom de hjälper till att korta URL-längden för en bildförfrågan. Se [Dynamiska variabler](../page-vars/dynamic-variables.md) för mer information om detta koncept.

Som standard använder dynamiska variabler prefixet `D=`. The `dynamicVariablePrefix` kan du anpassa strängen som identifierar dynamiska variabler. Den är skiftlägeskänslig.

## Dynamiskt variabelprefix med Web SDK

I Web SDK används inte dynamisk variabelformatering. I stället kan du använda Datastream-mappning för att fylla i flera målfält med ett enda källfält. Se [Dynamiska variabler med Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) för mer information.

## Dynamiskt variabelprefix med Adobe Analytics-tillägget

Dynamiskt variabelprefix är ett fält under [!UICONTROL Global Variables] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera [!UICONTROL Global Variables] dragspelspanel, som visar [!UICONTROL Dynamic Variable Prefix] fält.

Det här fältet innehåller `D=` som standard. Du kan ändra värdet om du vill använda ett annat dynamiskt variabelprefix. Du kan använda vilket värde du vill, förutsatt att det matchar teckenkodningen på webbplatsen.

## s.dynamicVariablePrefix i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.dynamicVariablePrefix` variabeln är en sträng som kan innehålla vilken teckensekvens som helst. Om variabeln inte är definierad använder AppMeasurement strängen `D=` som standard.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
