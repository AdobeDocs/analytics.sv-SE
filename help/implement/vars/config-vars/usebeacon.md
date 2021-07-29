---
title: useBeacon
description: Med useBeacon kan du tvinga AppMeasurement att använda webbläsarnas sendBeacon-API
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# useBeacon

De flesta moderna webbläsare innehåller den inbyggda metoden `navigator.sendBeacon()`. Den skickar asynkront en liten mängd data via HTTP till en webbserver. AppMeasurement kan använda metoden `navigator.sendBeacon()` om variabeln `useBeacon` är aktiverad. Det är användbart för att avsluta länkar och andra situationer där du vill skicka information innan sidan tas bort.

Om `useBeacon` är aktiverat använder nästa träff som skickas till Adobe webbläsarens `navigator.sendBeacon()`-metod i stället för en vanlig `GET`-bildbegäran. Den här variabeln gäller för både [`s.t()`](../functions/t-method.md)- och [`s.tl()`](../functions/tl-method.md)-bildbegäranden. AppMeasurement 2.17.0 eller senare krävs.

>[!TIP]
>
>AppMeasurement aktiverar automatiskt `useBeacon` för att avsluta länkbildsbegäranden.

Variabeln `useBeacon` ignoreras när besökaren använder en webbläsare som inte stöder `navigator.sendBeacon()`. Användning av den här variabeln kräver AppMeasurement 2.16.0 eller senare.

## Använd Beacon med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.useBeacon i AppMeasurement och anpassad kodredigerare

Variabeln `s.useBeacon` är en boolesk variabel som avgör om AppMeasurement använder webbläsarens `navigator.sendBeacon()`-metod. Dess standardvärde är `false`. Ställ in variabeln på `true` innan du anropar en spårningsfunktion om du vill använda den asynkrona typen `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>När ett spårningsanrop har körts återställs variabeln till `false`. Om implementeringen skickar flera bildbegäranden i samma sidinläsning (till exempel enkelsidiga program), ställer du in den här variabeln på `true` före varje spårningsanrop.
