---
title: usePlugins
description: Aktivera eller inaktivera funktionen doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# usePlugins

Om `usePlugins` är aktiverat körs funktionen [`doPlugins()`](../functions/doplugins.md) precis innan AppMeasurement kompilerar och skickar en träff till Adobe. Aktivera variabeln om du använder funktionen `doPlugins()`.

## Använd motringningen `onBeforeEventSend` med SDK för webben

SDK på webben har ingen boolesk funktion som hanterar körningen av ytterligare logik innan data skickas till Adobe, men du kan registrera återanropet `onBeforeEventSend` för att ändra data. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#modifying-events-globally) i Web SDK-dokumentationen.

## Använda plugin-program med Adobe Analytics-tillägget

Adobe tillhandahåller ett tillägg med namnet&quot;Common Analytics Plugins&quot; som gör att du kan anropa de flesta [plugin-program](../plugins/impl-plugins.md). Installera tillägget och anropa önskat plugin-program i en regel.

Om det plugin-program du vill använda inte ingår i Adobe-tillägget använder du den anpassade kodredigeraren efter AppMeasurement syntax.

## s.usePlugins i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.usePlugins` är en boolesk variabel som avgör om AppMeasurement anropar funktionen `doPlugins()`. Dess standardvärde är `false`. Ange variabeln till `true` om du använder funktionen `doPlugins()` i implementeringen.

```js
s.usePlugins = true;
```
