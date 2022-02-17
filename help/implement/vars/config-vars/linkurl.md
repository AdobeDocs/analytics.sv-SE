---
title: linkURL
description: Åsidosätt den automatiskt genererade länken URL AppMeasurement använder i länkspårningsanrop.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# linkURL

När ett anrop om länkspårning skickas till Adobe identifierar datainsamlingsservrarna automatiskt URL:en. Använd `linkURL` variabel som åsidosätter den identifierade URL:en.

## Länka URL med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.linkURL i AppMeasurement och anpassad kodredigerare

The `s.linkURL` variabeln är en sträng som innehåller webbläsarens URL när användaren klickar på länken. Den här variabeln fyller inte i några dimensioner som är tillgängliga i rapporter.

```js
s.linkURL = "https://example.com";
```

Om det tredje argumentet i [tl()](../functions/tl-method.md) metoden är inte inställd, `linkURL` används i stället.
