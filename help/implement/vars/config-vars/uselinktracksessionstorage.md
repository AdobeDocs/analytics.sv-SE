---
title: useLinkTrackSessionStorage
description: Lagra länkspårningsdata i sessionslagring i stället för en cookie.
translation-type: tm+mt
source-git-commit: 1b8de7489be8461707307dfe99d86f46557c7b8b

---


# useLinkTrackSessionStorage

Om din organisation använder länkspårning använder AppMeasurement cookie-filen för att skicka information mellan träffar. `s_sq` Vissa webbplatskonfigurationer är i konflikt med den här cookien. Aktivera den här variabeln om du vill använda webbläsarsessionslagring för länkspårning och aktivitetskarta i stället för en cookie.

En webbläsares sessionslagring för länkspårning har flera begränsningar:

* Sessionslagring fungerar inte mellan protokoll. Du kan till exempel ha en sida som skickas över HTTP och nästa sida som skickas via HTTPS. AppMeasurement kan inte komma åt länkspårningsdata i sessionslagring på grund av protokollskillnader.
* Sessionslagring fungerar inte i alla underdomäner. En besökare navigerar till exempel till `store.example.com`och navigerar sedan till `toys.example.com`. AppMeasurement kan inte komma åt länkspårningsdata i sessionslagring på grund av olika underdomäner.

> [!TIP] Den mest tillförlitliga implementeringen med sessionslagring för länkspårning levererar allt innehåll via HTTPS på en enda underdomän.

AppMeasurement tar bort länkspårningsdata för sessionslagring när en träff har skickats till Adobe. Den förfaller automatiskt när webbläsarfliken stängs.

## Använd sessionslagring för länkspår i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.useLinkTrackSessionStorage i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.useLinkTrackSessionStorage` är en boolesk variabel som avgör om AppMeasurement använder sessionslagring för länkspårningsdata i stället för `s_sq` cookie-filen. Dess standardvärde är `false`. Ange variabeln till `true` om du vill att AppMeasurement ska använda sessionslagring i stället för `s_sq` cookie-filen för länkspårning och aktivitetskarta.

```js
s.useLinkTrackSessionStorage = true;
```
