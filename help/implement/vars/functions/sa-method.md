---
title: sa
description: Ändra rapportsviten när som helst i implementeringen.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# sa

Med den här `sa` metoden kan du dynamiskt ändra en rapportsserie när som helst på sidan. Om du vill skicka data till olika rapportsviter utan att behöva läsa in en sida igen kan du använda den här metoden.

## Använd metoden sa i Adobe Experience Platform Launch

Det finns inget flexibelt sätt att ändra rapportsviten i gränssnittet. Du kan ställa in rapportsviten under dragspelet [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget. Du kan dock inte ändra eller uppdatera rapportsviten med hjälp av regler. Om du vill uppdatera rapportsvitens värden när de har angetts använder du den anpassade kodredigeraren efter AppMeasurement-syntaxen.

## s.sa() i AppMeasurement och Launch, anpassad kodredigerare

Anropa `s.sa()` metoden för att ändra målrapportsviten. Det enda argumentet är en sträng som innehåller ett rapportsuite-ID, eller flera rapportsuite-ID:n avgränsade med kommatecken. Argumentet för rapportsvitens ID krävs. Använd inte blanksteg i strängargumentet.

```js
s.sa("examplersid");
```

## Exempel

Du kan ändra rapportsviten om användaren utför en viss åtgärd på webbplatsen.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
