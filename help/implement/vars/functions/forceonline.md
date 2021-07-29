---
title: forceOnline
description: Ange onlinetillståndet för AppMeasurement manuellt.
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# forceOnline

Med metoden `forceOnline()` kan du åsidosätta det automatiskt identifierade tillståndet för AppMeasurement.

>[!IMPORTANT]
>
>Använd bara den här metoden när [`trackOffline`](../config-vars/trackoffline.md) är aktiverat. Om den här funktionen används utanför spårning offline kan data gå förlorade.

AppMeasurement identifierar automatiskt enhetens onlineläge. Du kan använda metoden `forceOnline()` för att tvinga AppMeasurement att behandla träffar som om enheten var online. Den här metoden tar inga argument och returnerar inget värde. Dess enda syfte är att åsidosätta onlinetillståndet i AppMeasurement.

## Tvinga online med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.forceOnline() i AppMeasurement och anpassad kodredigerare

Du kan anropa metoden `s.forceOnline()` var som helst i implementeringen efter att du har initierat Analytics-objektet.

```js
s.forceOnline();
```
