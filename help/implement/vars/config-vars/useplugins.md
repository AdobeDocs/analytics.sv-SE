---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# usePlugins

If `usePlugins` är aktiverat, [`doPlugins()`](../functions/doplugins.md) funktionen körs precis innan AppMeasurement kompileras och skickar en träff till Adobe. Aktivera den här variabeln om du använder `doPlugins()` funktion.

## Använd `onBeforeEventSend` återanrop med Web SDK

Även om Web SDK inte har ett booleskt värde för att hantera exekveringen av ytterligare logik innan data skickas till Adobe kan du registrera `onBeforeEventSend` återanrop för att ändra data. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) i Web SDK-dokumentationen om du vill ha mer information.

## Använda plugin-program med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.usePlugins i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.usePlugins` variabeln är ett booleskt värde som avgör om AppMeasurement anropar `doPlugins()` funktion. Standardvärdet är `false`. Ange variabeln till `true` om du använder `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
