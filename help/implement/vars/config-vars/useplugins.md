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

Om `usePlugins` är aktiverat körs funktionen [`doPlugins()`](../functions/doplugins.md) precis innan AppMeasurementet kompileras och skickar en träff till Adobe. Aktivera variabeln om du använder funktionen `doPlugins()`.

## Använd motringningen `onBeforeEventSend` med Web SDK

Web SDK har inget booleskt värde för att hantera körningen av ytterligare logik innan data skickas till Adobe, men du kan registrera `onBeforeEventSend`-återanropet för att ändra data. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) i Web SDK-dokumentationen.

## Använda plugin-program med Adobe Analytics-tillägget

Adobe tillhandahåller ett tillägg med namnet&quot;Common Analytics Plugins&quot; som gör att du kan anropa de flesta [plugin-program](../plugins/impl-plugins.md). Installera tillägget och anropa önskat plugin-program i en regel.

Om det plugin-program du vill använda inte ingår i tillägget Adobe använder du den anpassade kodredigeraren efter AppMeasurementen syntax.

## s.usePlugins i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.usePlugins` är en boolesk variabel som avgör om AppMeasurementet anropar funktionen `doPlugins()`. Dess standardvärde är `false`. Ange variabeln till `true` om du använder funktionen `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
