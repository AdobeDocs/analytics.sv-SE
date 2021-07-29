---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 2%

---

# usePlugins

Om `usePlugins` är aktiverat körs funktionen [`doPlugins()`](../functions/doplugins.md) precis innan AppMeasurement kompileras och skickar en träff till Adobe. Aktivera den här variabeln om du använder funktionen `doPlugins()`.

## Använda plugin-program med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.usePlugins i AppMeasurement och anpassad kodredigerare

Variabeln `s.usePlugins` är en boolesk variabel som avgör om AppMeasurement anropar funktionen `doPlugins()`. Dess standardvärde är `false`. Ange den här variabeln till `true` om du använder funktionen `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
