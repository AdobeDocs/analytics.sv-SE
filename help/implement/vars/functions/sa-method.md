---
title: sa
description: Ändra rapportsviten när som helst i implementeringen.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# sa

The `sa()` kan du när som helst på sidan dynamiskt ändra en rapportserie. Om du vill skicka data till olika rapportsviter utan att behöva läsa in en sida igen kan du använda den här metoden.

## Använd metoden sa med taggar i Adobe Experience Platform

Det finns inget flexibelt sätt att ändra rapportsviten i gränssnittet. Du kan ange rapportsviten under [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget. Du kan dock inte ändra eller uppdatera rapportsviten med hjälp av regler. Om du vill uppdatera rapportsvitens värden när de har angetts använder du den anpassade kodredigeraren efter AppMeasurement-syntaxen.

## s.sa() i AppMeasurement och anpassad kodredigerare

Ring `s.sa()` metod för att ändra målrapportsviten. Det enda argumentet är en sträng som innehåller ett rapportsuite-ID, eller flera rapportsuite-ID:n avgränsade med kommatecken. Argumentet för rapportsvitens ID krävs. Använd inte blanksteg i strängargumentet.

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
