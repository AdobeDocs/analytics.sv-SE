---
title: useLinkTrackSessionStorage
description: Lagra länkspårningsdata i sessionslagring i stället för en cookie.
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# useLinkTrackSessionStorage

Om din organisation använder länkspårning använder AppMeasurement `s_sq` cookie för att skicka information mellan träffar. Vissa webbplatskonfigurationer är i konflikt med den här cookien. Aktivera den här variabeln om du vill använda webbläsarsessionslagring för länkspårning och Activity Map i stället för en cookie.

En webbläsares sessionslagring för länkspårning har flera begränsningar:

* Sessionslagring fungerar inte mellan protokoll. Du kan till exempel ha en sida som skickas över HTTP och nästa sida som skickas via HTTPS. AppMeasurement kan inte komma åt länkspårningsdata i sessionslagring på grund av protokollskillnader.
* Sessionslagring fungerar inte i alla underdomäner. En besökare navigerar till exempel till `store.example.com`navigerar sedan till `toys.example.com`. AppMeasurement kan inte komma åt länkspårningsdata i sessionslagring på grund av olika underdomäner.

>[!TIP]
>
>Den mest tillförlitliga implementeringen med sessionslagring för länkspårning levererar allt innehåll via HTTPS på en enda underdomän.

AppMeasurement tar bort spårningsdata för sessionslagringslänkar efter att en träff har skickats till Adobe. Den förfaller automatiskt när webbläsarfliken stängs.

## Använda länkspårssessionslagring med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.useLinkTrackSessionStorage i AppMeasurement och anpassad kodredigerare

The `s.useLinkTrackSessionStorage` variabeln är en boolesk variabel som avgör om AppMeasurement använder sessionslagring för länkspårningsdata i stället för `s_sq` cookie. Standardvärdet är `false`. Ange variabeln till `true` om du vill att AppMeasurement ska använda sessionslagring i stället för `s_sq` cookie för länkspårning och Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
