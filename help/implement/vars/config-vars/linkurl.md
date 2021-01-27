---
title: linkURL
description: Åsidosätt den automatiskt genererade länken URL AppMeasurement använder i länkspårningsanrop.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 1%

---


# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd variabeln `linkURL` för att åsidosätta den URL som identifierats.

## Länk-URL i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.linkURL i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.linkURL` är en sträng som innehåller URL-adressen för webbläsaren när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet för metoden [tl()](../functions/tl-method.md) inte är inställt används variabeln `linkURL` i stället.
