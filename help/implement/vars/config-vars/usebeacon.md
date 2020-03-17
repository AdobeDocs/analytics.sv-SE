---
title: useBeacon
description: Med useBeacon kan du tvinga AppMeasurement att använda webbläsarnas sendBeacon-API
translation-type: tm+mt
source-git-commit: 58513f012bdbd1143601221985a399ed46916664

---


# useBeacon

I de flesta moderna webbläsare finns den inbyggda metoden `navigator.sendBeacon()`. Den skickar asynkront en liten mängd data via HTTP till en webbserver. AppMeasurement kan använda `navigator.sendBeacon()` metoden om `useBeacon` variabeln är aktiverad. Det är användbart för att avsluta länkar och andra situationer där du vill skicka information innan sidan tas bort.

Om `useBeacon` alternativet är aktiverat används webbläsarens `navigator.sendBeacon()` metod i nästa träff som skickas till Adobe i stället för en standardbegäran om `GET` bilder. Den här variabeln gäller för både `s.t()` - och `s.tl()` bildbegäranden. AppMeasurement 2.17.0 eller senare krävs.

> [!TIP] AppMeasurement aktiverar automatiskt `useBeacon` för att avsluta länkbildsförfrågningar.

Variabeln `useBeacon` ignoreras när besökaren använder en webbläsare som inte stöder `navigator.sendBeacon()`. Användning av den här variabeln kräver AppMeasurement 2.16.0 eller senare.

## Använd Beacon i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.useBeacon i AppMeasurement and Launch custom code editor

Variabeln `s.useBeacon` är en boolesk variabel som avgör om AppMeasurement använder webbläsarens `navigator.sendBeacon()` metod. Dess standardvärde är `false`. Ange variabeln till `true` innan du anropar en spårningsfunktion om du vill använda den asynkrona typen av `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

> [!NOTE] När ett spårningsanrop har körts återställs variabeln till `false`. Om implementeringen skickar flera bildbegäranden i samma sidinläsning (t.ex. enkelsidiga program), ställer du in variabeln på `true` före varje spårningsanrop.
