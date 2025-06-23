---
title: trackOffline
description: Aktivera eller inaktivera spårning offline, vilket ändrar hur AppMeasurement samlar in data.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# trackOffline

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

Variabeln `trackOffline` avgör om du vill använda offlinespårning i implementeringen.

>[!WARNING]
>
>Du måste konfigurera rapportsviten så att den godkänner tidsstämplade träffar innan du aktiverar variabeln. Om en rapportsvit inte accepterar tidsstämplade träffar och variabeln är aktiverad går dessa data förlorade och kan inte återställas.

När det här alternativet är aktiverat använder AppMeasurement följande process för att skicka data till Adobe:

* När en bildbegäran kompileras inkluderas en frågesträngsparameter för tidsstämpling.
* Om enheten inte kan nå Adobe datainsamlingsservrar lagras träffen lokalt på enheten.
* Under varje efterföljande träff försöker AppMeasurement skicka en bildförfrågan till Adobe.
   * Om det inte kan nå Adobe datainsamlingsservrar läggs träffen till i kön på enheten.
   * Om den kan nå Adobe datainsamlingsservrar skickas träffen och kön för träffar när enheten var offline.

## Spårning offline med Web SDK

SDK för webben stöder inte spårning offline.

## Spårning offline med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.trackOffline i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.trackOffline` är en boolesk variabel som aktiverar eller inaktiverar offlinespårning. Dess standardvärde är `false`. Ange det här värdet till `true` om du vill aktivera offlinespårning.

```js
s.trackOffline = true;
```
