---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# usePlugins

If `usePlugins` är aktiverat, [`doPlugins()`](../functions/doplugins.md) funktionen körs precis innan AppMeasurementet kompileras och en träff skickas till Adobe. Aktivera variabeln om du använder `doPlugins()` funktion.

## Använd `onBeforeEventSend` återanrop med Web SDK

Även om Web SDK inte har ett booleskt värde för att hantera körningen av ytterligare logik innan data skickas till Adobe kan du registrera `onBeforeEventSend` återanrop för att ändra data. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) finns i Web SDK-dokumentationen.

## Använda plugin-program med Adobe Analytics-tillägget

Adobe har ett tillägg med namnet&quot;Common Analytics Plugins&quot; som gör att du kan ringa de flesta [Plugin-program](../plugins/impl-plugins.md). Installera tillägget och anropa önskat plugin-program i en regel.

Om det plugin-program du vill använda inte ingår i tillägget Adobe använder du den anpassade kodredigeraren efter AppMeasurementen syntax.

## s.usePlugins i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.usePlugins` är en boolesk variabel som avgör om AppMeasurementet anropar `doPlugins()` funktion. Standardvärdet är `false`. Ange variabeln till `true` om du använder `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
