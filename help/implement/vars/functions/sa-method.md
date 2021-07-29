---
title: sa
description: Ändra rapportsviten när som helst i implementeringen.
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# sa

Med metoden `sa()` kan du dynamiskt ändra en rapportserie när som helst på sidan. Om du vill skicka data till olika rapportsviter utan att behöva läsa in en sida igen kan du använda den här metoden.

## Använd metoden sa med taggar i Adobe Experience Platform

Det finns inget flexibelt sätt att ändra rapportsviten i gränssnittet. Du kan ställa in rapportsviten under dragspelet [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget. Du kan dock inte ändra eller uppdatera rapportsviten med hjälp av regler. Om du vill uppdatera rapportsvitens värden när de har angetts använder du den anpassade kodredigeraren efter AppMeasurement-syntaxen.

## s.sa() i AppMeasurement och anpassad kodredigerare

Anropa metoden `s.sa()` om du vill ändra målrapportsviten. Det enda argumentet är en sträng som innehåller ett rapportsuite-ID, eller flera rapportsuite-ID:n avgränsade med kommatecken. Argumentet för rapportsvitens ID krävs. Använd inte blanksteg i strängargumentet.

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
