---
title: forceOffline
description: Ange AppMeasurementets onlinestatus manuellt.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# forceOffline

Med metoden `forceOffline()` kan du åsidosätta det automatiskt identifierade AppMeasurementet.

>[!WARNING]
>
>Använd bara den här funktionen när [`trackOffline`](../config-vars/trackoffline.md) är aktiverad. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurementet identifierar automatiskt enhetens onlineläge. Du kan använda metoden `forceOffline()` för att tvinga AppMeasurementet att behandla träffar som om enheten var offline. Den här metoden tar inga argument och returnerar inget värde. Det enda syftet är att åsidosätta onlinetillståndet i AppMeasurementet.

## Tvinga offline med Web SDK

Web SDK stöder inte offlinespårning.

## Tvinga offline med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.forceOffline() i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Du kan anropa metoden `s.forceOffline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOffline();
```
