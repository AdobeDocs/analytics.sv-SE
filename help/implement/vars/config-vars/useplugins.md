---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 2%

---

# usePlugins

If `usePlugins` är aktiverat, [`doPlugins()`](../functions/doplugins.md) funktionen körs precis innan AppMeasurement kompileras och skickar en träff till Adobe. Aktivera den här variabeln om du använder `doPlugins()` funktion.

## Använda plugin-program med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.usePlugins i AppMeasurement och anpassad kodredigerare

The `s.usePlugins` variabeln är ett booleskt värde som avgör om AppMeasurement anropar `doPlugins()` funktion. Standardvärdet är `false`. Ange variabeln till `true` om du använder `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
