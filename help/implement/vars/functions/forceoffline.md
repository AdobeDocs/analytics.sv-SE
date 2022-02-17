---
title: forceOffline
description: Ange onlinetillståndet för AppMeasurement manuellt.
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# forceOffline

The `forceOffline()` kan du åsidosätta det automatiskt identifierade läget för AppMeasurement.

>[!IMPORTANT]
>
>Använd bara den här funktionen när [`trackOffline`](../config-vars/trackoffline.md) är aktiverat. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda `forceOffline()` metod som tvingar AppMeasurement att behandla träffar som om enheten var offline. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga offlineanvändning med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOffline() i AppMeasurement och anpassad kodredigerare

Du kan ringa `s.forceOffline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOffline();
```
