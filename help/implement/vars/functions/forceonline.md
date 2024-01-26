---
title: forceOnline
description: Ange AppMeasurementets onlinestatus manuellt.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# forceOnline

The `forceOnline()` kan du åsidosätta det automatiskt identifierade AppMeasurementet.

>[!WARNING]
>
>Använd bara den här metoden när [`trackOffline`](../config-vars/trackoffline.md) är aktiverat. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurementet identifierar automatiskt enhetens onlineläge. Du kan använda `forceOnline()` metod som tvingar AppMeasurementet att behandla träffar som om enheten var online. Den här metoden tar inga argument och returnerar inget värde. Det enda syftet är att åsidosätta onlinetillståndet i AppMeasurementet.

## Tvinga online med Web SDK

Web SDK stöder inte offlinespårning.

## Tvinga online med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.forceOnline() i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Du kan ringa `s.forceOnline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOnline();
```
