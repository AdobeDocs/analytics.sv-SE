---
title: forceOffline
description: Ange onlinetillståndet för AppMeasurement manuellt.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# forceOffline

The `forceOffline()` kan du åsidosätta det automatiskt identifierade läget för AppMeasurement.

>[!WARNING]
>
>Använd bara den här funktionen när [`trackOffline`](../config-vars/trackoffline.md) är aktiverat. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda `forceOffline()` metod som tvingar AppMeasurement att behandla träffar som om enheten var offline. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga offline med Web SDK

Web SDK stöder inte offlinespårning.

## Tvinga offline med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOffline() i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

Du kan ringa `s.forceOffline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOffline();
```
