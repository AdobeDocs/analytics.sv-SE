---
title: linkURL
description: Åsidosätt den automatiskt genererade länken URL AppMeasurement använder i länkspårningsanrop.
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd variabeln `linkURL` för att åsidosätta den URL som identifierats.

## Länka URL med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.linkURL i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkURL` är en sträng som innehåller URL-adressen för webbläsaren när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet för metoden [tl()](../functions/tl-method.md) inte är inställt används variabeln `linkURL` i stället.
