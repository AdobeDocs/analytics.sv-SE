---
title: forceOnline
description: Ange onlinetillståndet för AppMeasurement manuellt.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# forceOnline

The `forceOnline()` kan du åsidosätta det automatiskt identifierade läget för AppMeasurement.

>[!WARNING]
>
>Använd bara den här metoden när [`trackOffline`](../config-vars/trackoffline.md) är aktiverat. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda `forceOnline()` metod som tvingar AppMeasurement att behandla träffar som om enheten var online. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga online med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOnline() i AppMeasurement och anpassad kodredigerare

Du kan ringa `s.forceOnline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOnline();
```
