---
title: useLinkTrackSessionStorage
description: Lagra länkspårningsdata i sessionslagring i stället för en cookie.
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# useLinkTrackSessionStorage

Om din organisation använder länkspårning använder AppMeasurement cookien `s_sq` för att skicka information mellan träffar. Vissa webbplatskonfigurationer är i konflikt med den här cookien. Aktivera den här variabeln om du vill använda webbläsarsessionslagring för länkspårning och Activity Map-data i stället för en cookie.

En webbläsares sessionslagring för länkspårning har flera begränsningar:

* Sessionslagring fungerar inte mellan protokoll. Du kan till exempel ha en sida som skickas över HTTP och nästa sida som skickas via HTTPS. AppMeasurement har inte åtkomst till länkspårningsdata i sessionslagring på grund av protokollskillnader.
* Sessionslagring fungerar inte i alla underdomäner. En besökare navigerar till exempel till `store.example.com` och sedan till `toys.example.com`. AppMeasurement har inte åtkomst till länkspårningsdata i sessionslagring på grund av olika underdomäner.

>[!TIP]
>
>Den mest tillförlitliga implementeringen med sessionslagring för länkspårning levererar allt innehåll via HTTPS på en enda underdomän.

AppMeasurement tar bort spårningsdata för sessionslagringslänk efter att en träff har skickats till Adobe. Den förfaller automatiskt när webbläsarfliken stängs.

## Använd länkspårssessionslagring med SDK

Web SDK stöder inte den här funktionen.

## Använd sessionsarkiv för länkspår med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.useLinkTrackSessionStorage i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.useLinkTrackSessionStorage` är en boolesk variabel som avgör om AppMeasurement använder sessionslagring för länkspårningsdata i stället för `s_sq`-cookien. Dess standardvärde är `false`. Ange den här variabeln till `true` om du vill att AppMeasurement ska använda sessionslagring i stället för `s_sq` cookie-filen för länkspårning och Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
