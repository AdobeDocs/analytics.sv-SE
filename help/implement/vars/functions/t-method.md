---
title: t
description: Skicka ett spårningsanrop för sidvy till Adobe.
translation-type: tm+mt
source-git-commit: 8494e8bb08b45006b357dd114e6bf9507f0cd54a

---


# t

Metoden är en viktig `t` komponent i Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar dessa data till Adobes datainsamlingsservrar.

Titta på följande JavaScript-kod:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

När du kör `t` metoden används alla definierade Analytics-variabler och en URL som baseras på dessa variabler skapas. Vissa analysvariabler bestämmer URL:en för bilden, medan andra variabler bestämmer parametervärden för frågesträngar.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe tar emot bildbegäran och tolkar sedan parametrarna request header, URL och query string. Datainsamlingsservrar returnerar sedan en genomskinlig 1x1-pixelbild som visas osynligt på din webbplats.

## Anrop om spårning av sidvy i Adobe Experience Platform Launch

Launch har en dedikerad plats där ett spårningsanrop för sidvy har angetts.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på ikonen + [!UICONTROL Actions]under
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] &quot; [!UICONTROL Action Type] Skicka Beacon&quot;.
6. Klicka på `s.t()` alternativknappen.

## s.t()-metoden i AppMeasurement och den anpassade kodredigeraren Launch

Anropa `s.t()` metoden när du vill skicka ett spårningsanrop till Adobe.

```js
s.t();
```

Du kan också använda ett objekt som argument för att åsidosätta variabelvärden. Mer information finns i [Variabelåsidosättningar](../../js/overrides.md) .

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] I tidigare versioner av AppMeasurement användes flera kodrader för att anropa den här funktionen. Den extra koden rymmer temporärt tillfälliga lösningar för olika webbläsare. Det här kodblocket behövs inte längre för standardisering och bästa praxis i moderna webbläsare. Nu `s.t()` behövs bara metodanropet.
