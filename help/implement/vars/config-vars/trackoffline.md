---
title: trackOffline
description: Aktivera eller inaktivera spårning offline, vilket ändrar hur AppMeasurementet samlar in data.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# trackOffline

Spårning offline är ett valfritt sätt att samla in data i Adobe Analytics. Om en besökare kopplar från Internet men fortsätter att surfa på webbplatsen, lagras träffarna i en offlinekö tills enheten återansluter till Internet. Spårning offline används oftast för mobilprogram.

The `trackOffline` variabeln avgör om du vill använda offline-spårning i implementeringen.

>[!WARNING]
>
>Du måste konfigurera rapportsviten så att den godkänner tidsstämplade träffar innan du aktiverar variabeln. Om en rapportsvit inte accepterar tidsstämplade träffar och variabeln är aktiverad går dessa data förlorade och kan inte återställas.

När AppMeasurementet är aktiverat används följande process för att skicka data till Adobe:

* När en bildbegäran kompileras inkluderas en frågesträngsparameter för tidsstämpling.
* Om enheten inte kan nå datainsamlingsservrarna i Adobe lagras träffen lokalt på enheten.
* Under varje efterföljande träff försöker AppMeasurementet skicka en bildbegäran till Adobe.
   * Om det inte går att nå datainsamlingsservrar från Adobe läggs träffen till i kön på enheten.
   * Om den kan nå datainsamlingsservrar i Adobe skickas träffen och kön för träffar när enheten var offline.

## Spårning offline med Web SDK

Web SDK stöder inte offlinespårning.

## Spårning offline med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.trackOffline i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.trackOffline` är en boolesk variabel som aktiverar eller inaktiverar spårning offline. Standardvärdet är `false`. Ange det här värdet till `true` om du vill aktivera spårning offline.

```js
s.trackOffline = true;
```
