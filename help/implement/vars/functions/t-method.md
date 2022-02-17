---
title: t
description: Skicka ett spårningsanrop för sidvy till Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '271'
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

## Anrop till spårning av sidvy med hjälp av taggar i Adobe Experience Platform

Användargränssnittet för datainsamling har en dedikerad plats som anger ett spårningsanrop för sidvyn.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på plustecknet (+)
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] för att skicka Beacon.
6. Klicka på `s.t()` alternativknapp.

## s.t(), metod i AppMeasurement och anpassad kodredigerare

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
