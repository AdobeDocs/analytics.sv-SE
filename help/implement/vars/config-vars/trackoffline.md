---
title: trackOffline
description: Aktivera eller inaktivera spårning offline, vilket ändrar hur AppMeasurement samlar in data.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# trackOffline

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

The `trackOffline` variabeln avgör om du vill använda offline-spårning i implementeringen.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsviten så att den godkänner tidsstämplade träffar innan du aktiverar variabeln. Om en rapportsvit inte accepterar tidsstämplade träffar och variabeln är aktiverad går dessa data förlorade och kan inte återställas.

När det är aktiverat använder AppMeasurement följande process för att skicka data till Adobe:

* När en bildbegäran kompileras inkluderas en frågesträngsparameter för tidsstämpling.
* Om enheten inte kan nå datainsamlingsservrarna i Adobe lagras träffen lokalt på enheten.
* Under varje efterföljande träff försöker AppMeasurement skicka en bildbegäran till Adobe.
   * Om det inte går att nå datainsamlingsservrar från Adobe läggs träffen till i kön på enheten.
   * Om den kan nå datainsamlingsservrar i Adobe skickas träffen och kön för träffar när enheten var offline.

## Spåra offline med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.trackOffline i AppMeasurement och anpassad kodredigerare

The `s.trackOffline` är en boolesk variabel som aktiverar eller inaktiverar spårning offline. Standardvärdet är `false`. Ange det här värdet till `true` om du vill aktivera spårning offline.

```js
s.trackOffline = true;
```
