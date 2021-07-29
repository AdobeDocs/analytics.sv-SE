---
title: dynamicVariablePrefix
description: Gör att du kan anpassa strängen som identifierar dynamiska variabler.
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# dynamicVariablePrefix

Dynamiska variabler är ett koncept med vilket du kan kopiera värden från en variabel till en annan. De är användbara för långa variabelvärden eftersom de hjälper till att korta URL-längden för en bildförfrågan. Mer information om detta koncept finns i [Dynamiska variabler](../page-vars/dynamic-variables.md).

Som standard använder dynamiska variabler prefixet `D=`. Med variabeln `dynamicVariablePrefix` kan du anpassa strängen som identifierar dynamiska variabler. Den är skiftlägeskänslig.

## Dynamiskt variabelprefix med taggar i Adobe Experience Platform

Dynamiskt variabelprefix är ett fält under dragspelet [!UICONTROL Global Variables] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Global Variables], som visar fältet [!UICONTROL Dynamic Variable Prefix].

Det här fältet innehåller som standard `D=`. Du kan ändra värdet om du vill använda ett annat dynamiskt variabelprefix. Du kan använda vilket värde du vill, förutsatt att det matchar teckenkodningen på webbplatsen.

## s.dynamicVariablePrefix i AppMeasurement och anpassad kodredigerare

Variabeln `s.dynamicVariablePrefix` är en sträng som kan innehålla vilken teckensekvens som helst. Om variabeln inte definieras används strängen `D=` som standard i AppMeasurement.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
