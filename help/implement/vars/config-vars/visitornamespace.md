---
title: visitorNameSpace
description: En indragen variabel som fastställde cookie-domän.
feature: Variables
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# visitorNamespace

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

I tidigare versioner av Adobe Analytics använde AppMeasurement `visitorNameSpace` variabel som hjälper till att fastställa underdomänen för `2o7.net` där besökarnas cookies lagras. Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. I och med introduktionen av `trackingServer` och [`trackingServerSecure`](trackingserversecure.md) variabler, `visitorNameSpace` behövs inte längre.

>[!TIP]
>
>Adobe rekommenderar att du använder cookies från första part på din webbplats. Den här variabeln används inte för cookies från första part.

## Namnutrymme för besökare med Adobe Analytics-tillägget

[!UICONTROL Visitor Namespace] är ett fält under [!UICONTROL Cookies] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Cookies] dragspelspanel, som visar [!UICONTROL Visitor Namespace] fält.

Adobe avråder från att använda det här fältet. Använd `trackingServer` och `trackingServerSecure` i stället.

## s.visitorNamespace i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.visitorNamespace` variabeln är en sträng som innehåller ett unikt värde per organisation. Gamla AppMeasurement-bibliotek har automatiskt inkluderat detta unika värde när de laddas ned från tidigare versioner av Adobe Analytics. Aktuella AppMeasurement-bibliotek använder inte den här variabeln såvida inte `trackingServer` och `trackingServerSecure` har inte angetts.

Om din organisation fortfarande behöver den här variabeln väljer du ett värde som representerar din organisation. Du kan lagra värdet i en [konstruktionsdokument](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
