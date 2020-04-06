---
title: linkName
description: Ange namnet på den anpassade länkträffen.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Använd variabeln `linkName` för att fastställa dimensionsvärdet för anpassade länkar, hämtningslänkar eller avslutslänkar när du kör nästa [`tl()`](../functions/tl-method.md) metod.

Om variabeln är tom återgår AppMeasurement till [`linkURL`](linkurl.md) -variabeln.

## Länknamn i Adobe Experience Platform Launch

Du kan ange länknamnsfältet när du konfigurerar en regel för att skicka en fyr.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på ikonen + [!UICONTROL Actions]under
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] &quot; [!UICONTROL Action Type] Skicka Beacon&quot;.
6. Klicka på den `s.tl()` alternativknapp som visar [!UICONTROL Link Name] fältet.

## s.linkName i AppMeasurement and Launch custom code editor

Variabeln `s.linkName` är en sträng som bestämmer dimensionsvärdet för anpassade länkar, hämtningslänkar eller avslutslänkar (beroende på vad som [`s.linkType`](linktype.md) är). Den kan innehålla upp till 100 byte.

>[!TIP] Den här variabeln är den tredje parametern i `tl()` metoden och behöver vanligtvis inte anges som en fristående variabel. Du kan dock använda variabeln om du inte vill ange värden som argument i `linkName` `tl()` metoden.

```js
s.linkName = "Example custom link";
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
