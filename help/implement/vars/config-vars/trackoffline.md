---
title: trackOffline
description: Aktivera eller inaktivera spårning offline, vilket ändrar hur AppMeasurement samlar in data.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackOffline

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

Variabeln avgör `trackOffline` om du vill använda offline-spårning i implementeringen.

> [!IMPORTANT] Du måste konfigurera rapportsviten så att den godkänner tidsstämplade träffar innan du aktiverar variabeln. Om en rapportsvit inte accepterar tidsstämplade träffar och variabeln är aktiverad går dessa data förlorade och kan inte återställas.

När det är aktiverat använder AppMeasurement följande process för att skicka data till Adobe:

* När en bildbegäran kompileras inkluderas en frågesträngsparameter för tidsstämpling.
* Om enheten inte kan nå Adobes datainsamlingsservrar lagras träffen lokalt på enheten.
* Under varje efterföljande träff försöker AppMeasurement skicka en bildförfrågan till Adobe.
   * Om det inte kan nå Adobes datainsamlingsservrar läggs träffen till i kön på enheten.
   * Om den kan nå Adobes datainsamlingsservrar skickas träffen och kön för träffar när enheten var offline.

## Spåra offline i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.trackOffline i AppMeasurement and Launch custom code editor

Variabeln är en boolesk variabel som aktiverar eller inaktiverar spårning offline. `s.trackOffline` Dess standardvärde är `false`. Ange det här värdet `true` om du vill aktivera spårning offline.

```js
s.trackOffline = true;
```
