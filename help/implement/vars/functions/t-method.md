---
title: t
description: Skicka ett spårningsanrop för sidvy till Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# t()

The `t()` är en viktig komponent i Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar data till datainsamlingsservrarna i Adobe.

Titta på följande JavaScript-kod:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

Kör `t()` -metoden använder alla definierade Analytics-variabler och skapar en URL som baseras på dessa variabler. Vissa analysvariabler bestämmer URL:en för bilden, medan andra variabler bestämmer parametervärden för frågesträngar.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe tar emot bildbegäran och tolkar sedan parametrarna för begärandehuvudet, URL:en och frågesträngen. Datainsamlingsservrar returnerar sedan en genomskinlig 1x1-pixelbild som visas osynligt på din webbplats.

## Skicka händelse med Web SDK-tillägget

Använd en åtgärd för att konfigurera sändning av XDM-händelsedata till Adobe. Datastream tar emot dessa data, tillämpar konfigurerade mappningar och vidarebefordrar dessa data till Adobe Analytics om det är en tillagd tjänst till det dataflödet.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
1. Under [!UICONTROL Actions]klickar du på funktionsmakrot eller klickar på **&#39;+&#39;** om du vill lägga till ett funktionsmakro.
1. Ange [!UICONTROL Extension] listruta till **[!UICONTROL Adobe Experience Platform Web SDK]** och [!UICONTROL Action Type] till **[!UICONTROL Send event]**.

## Skicka händelse manuellt som implementerar Web SDK

Använd `sendEvent` för att skicka data till Adobe. Datastream tar emot dessa data, tillämpar konfigurerade mappningar och vidarebefordrar dessa data till Adobe Analytics om det är en tillagd tjänst till det dataflödet.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Se [Spåra händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) i Web SDK-dokumentationen om du vill ha mer information.

## Anrop om spårning av sidvy med Adobe Analytics-tillägget

Adobe Analytics-tillägget i Adobe Experience Platform Data Collection har en dedikerad plats som anger ett spårningsanrop för sidvyn.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
1. Under [!UICONTROL Actions]klickar du på önskad åtgärd eller klickar på **&#39;+&#39;** om du vill lägga till ett funktionsmakro.
1. Ange [!UICONTROL Extension] listruta till **[!UICONTROL Adobe Analytics]** och [!UICONTROL Action Type] till **[!UICONTROL Send Beacon]**.
1. Klicka på `s.t()` alternativknapp.

## s.t()-metoden i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Ring `s.t()` när du vill skicka ett spårningsanrop till Adobe.

```js
s.t();
```

Du kan också använda ett objekt som argument för att åsidosätta variabelvärden. Se [variabelåsidosättningar](../../js/overrides.md) för mer information.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>I tidigare versioner av AppMeasurement användes flera kodrader för att anropa den här funktionen. Den extra koden rymmer temporärt tillfälliga lösningar för olika webbläsare. Det här kodblocket behövs inte längre för standardisering och bästa praxis i moderna webbläsare. Endast metodanropet `s.t()` behövs nu.
