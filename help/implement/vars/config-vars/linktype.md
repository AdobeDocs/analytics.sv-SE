---
title: linkType
description: Använd variabeln linkType för att avgöra vilken länkspårningsdimension träffen tillhör.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

Spårningsträffar för länkar kan fylla i en av tre dimensioner:

* Egna länkar
* Avsluta länkar
* Hämta länkar

Använd variabeln `linkType` för att bestämma vilken dimension du vill fylla i när du kör nästa `tl()` funktion.

## Länktyp i Adobe Experience Platform Launch

Ange länktypen när du konfigurerar en regel för att skicka en fyr.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på ikonen + [!UICONTROL Actions]under
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] &quot; [!UICONTROL Action Type] Skicka Beacon&quot;.
6. Klicka på den `s.tl()` alternativknapp som visar [!UICONTROL Link Type] listrutan.

Du kan ställa in den här listrutan till [!UICONTROL Custom Link], [!UICONTROL Download Link]eller [!UICONTROL Exit Link].

## s.linkType i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.linkType` är en sträng som accepterar ett av tre enkla teckenvärden: `o`, `d`eller `e`. Om en `tl()` funktion anropas utan en länktyp blir standardvärdet Anpassad länk.

* `o` - Anpassade länkar
* `d` - Hämta länkar
* `e` - Avsluta länkar

> [!TIP] Den här variabeln är den andra parametern i `tl()` funktionen och behöver vanligtvis inte anges som en fristående variabel. Du kan dock använda variabeln om du inte vill ange värden som argument i `linkType` `tl()` funktionen.

```js
s.linkType = "e";
```

## Exempel

Följande två exempel på länkspårningsanrop är funktionellt identiska. Det finns olika metoder för att uppnå samma länkspårningsträff.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
