---
title: t
description: Skicka ett spårningsanrop för sidvy till Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: e47bee837faf9b8cf080d878da860795ced014d5
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# t()

Metoden `t()` är en viktig kärnkomponent för Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar data till datainsamlingsservrarna i Adobe.

Ta till exempel följande JavaScript-kod:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

När du kör metoden `t()` används alla definierade Analytics-variabler och en URL som baseras på dessa variabler formuleras. Vissa analysvariabler bestämmer URL:en för bilden, medan andra variabler bestämmer parametervärden för frågesträngar.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

Adobe tar emot bildbegäran och tolkar sedan parametrarna för begärandehuvudet, URL:en och frågesträngen. Datainsamlingsservrar returnerar sedan en genomskinlig 1x1-pixelbild som visas osynligt på din webbplats.

## Skicka händelse med Web SDK-tillägget

Använd en åtgärd för att konfigurera sändning av XDM-händelsedata till Adobe. Datastream tar emot dessa data, tillämpar konfigurerade mappningar och vidarebefordrar dessa data till Adobe Analytics om det är en tillagd tjänst till det dataflödet.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
1. Klicka på önskad åtgärd under [!UICONTROL Actions] eller klicka på ikonen **+** för att lägga till en åtgärd.
1. Ställ in listrutan [!UICONTROL Extension] på **[!UICONTROL Adobe Experience Platform Web SDK]** och [!UICONTROL Action Type] på **[!UICONTROL Send event]**.

## Skicka händelse manuellt för att implementera Web SDK

Använd kommandot `sendEvent` för att skicka data till Adobe. Datastream tar emot dessa data, tillämpar konfigurerade mappningar och vidarebefordrar dessa data till Adobe Analytics om det är en tillagd tjänst till det dataflödet.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Mer information finns i [Spåra händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) i Web SDK-dokumentationen.

## Anrop om spårning av sidvy med Adobe Analytics-tillägget

Adobe Analytics-tillägget i Adobe Experience Platform Data Collection har en dedikerad plats som anger ett spårningsanrop för sidvyn.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
1. Klicka på önskad åtgärd under [!UICONTROL Actions] eller klicka på ikonen **+** för att lägga till en åtgärd.
1. Ställ in listrutan [!UICONTROL Extension] på **[!UICONTROL Adobe Analytics]** och [!UICONTROL Action Type] på **[!UICONTROL Send Beacon]**.
1. Klicka på alternativknappen `s.t()`.

## s.t()-metoden i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Anropa metoden `s.t()` när du vill skicka ett spårningsanrop till Adobe.

```js
s.t();
```

Du kan också använda ett objekt som argument för att åsidosätta variabelvärden. Mer information finns i [Variabelåsidosättningar](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>I tidigare versioner av AppMeasurementet anropades funktionen med flera kodrader. Den extra koden rymmer temporärt tillfälliga lösningar för olika webbläsare. Det här kodblocket behövs inte längre för standardisering och bästa praxis i moderna webbläsare. Endast metodanropet `s.t()` behövs nu.
