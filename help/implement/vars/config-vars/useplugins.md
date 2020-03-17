---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# usePlugins

Om `usePlugins` är aktiverat körs `doPlugins()` funktionen precis innan AppMeasurement kompileras och skickar en träff till Adobe. Aktivera den här variabeln om du använder `doPlugins()` funktionen.

## Använd plugin-program i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.usePlugins in AppMeasurement and Launch custom code editor

Variabeln `s.usePlugins` är en boolesk variabel som avgör om AppMeasurement anropar `doPlugins()` funktionen. Dess standardvärde är `false`. Ange variabeln till `true` om du använder `doPlugins()` funktionen i implementeringen.

```js
s.usePlugins = true;
```
