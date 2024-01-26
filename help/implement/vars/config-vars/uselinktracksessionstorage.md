---
title: useLinkTrackSessionStorage
description: Lagra länkspårningsdata i sessionslagring i stället för en cookie.
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# useLinkTrackSessionStorage

Om din organisation använder länkspårning används AppMeasurementet `s_sq` cookie för att skicka information mellan träffar. Vissa webbplatskonfigurationer är i konflikt med den här cookien. Aktivera den här variabeln om du vill använda webbläsarsessionslagring för länkspårning och Activity Map i stället för en cookie.

En webbläsares sessionslagring för länkspårning har flera begränsningar:

* Sessionslagring fungerar inte mellan protokoll. Du kan till exempel ha en sida som skickas över HTTP och nästa sida som skickas via HTTPS. AppMeasurementet har inte åtkomst till länkspårningsdata i sessionslagringen på grund av protokollskillnader.
* Sessionslagring fungerar inte i alla underdomäner. En besökare navigerar till exempel till `store.example.com`navigerar sedan till `toys.example.com`. AppMeasurementet kan inte komma åt länkspårningsdata i sessionslagring på grund av olika underdomäner.

>[!TIP]
>
>Den mest tillförlitliga implementeringen med sessionslagring för länkspårning levererar allt innehåll via HTTPS på en enda underdomän.

AppMeasurementet tar bort spårningsdata för sessionslagringslänkar när en träff har skickats till Adobe. Den förfaller automatiskt när webbläsarfliken stängs.

## Använd länkspårssessionslagring med Web SDK

Web SDK stöder inte den här funktionen.

## Använd sessionsarkiv för länkspår med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.useLinkTrackSessionStorage i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.useLinkTrackSessionStorage` är en boolesk variabel som avgör om AppMeasurementet använder sessionslagring för länkspårningsdata i stället för `s_sq` cookie. Standardvärdet är `false`. Ange variabeln till `true` om du vill att AppMeasurementet ska använda sessionslagring i stället för `s_sq` cookie för länkspårning och Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
