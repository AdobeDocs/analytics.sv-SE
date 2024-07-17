---
title: visitorNameSpace
description: (Borttaget) Hjälpte till att fastställa cookie-domän för tredje part.
feature: Variables
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---

# visitorNamespace

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

I tidigare versioner av Adobe Analytics använde AppMeasurementet variabeln `visitorNameSpace` för att avgöra underdomänen för `2o7.net` där besökares cookies lagras. Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. I och med introduktionen av variablerna `trackingServer` och [`trackingServerSecure`](trackingserversecure.md) behövs inte längre `visitorNameSpace`.

>[!TIP]
>
>Adobe rekommenderar att du använder cookies från första part på din webbplats. Den här variabeln används inte för cookies från första part.

## Namnutrymme för besökare med Adobe Analytics-tillägget

[!UICONTROL Visitor Namespace] är ett fält under dragspelet [!UICONTROL Cookies] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Cookies] som visar fältet [!UICONTROL Visitor Namespace].

Adobe avråder från att använda det här fältet. Använd `trackingServer` och `trackingServerSecure` i stället.

## s.visitorNamespace i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

Variabeln `s.visitorNamespace` är en sträng som innehåller ett unikt värde per organisation. Gamla AppMeasurement-bibliotek har automatiskt inkluderat detta unika värde när de laddas ned från tidigare versioner av Adobe Analytics. Aktuella AppMeasurement-bibliotek använder inte den här variabeln såvida inte `trackingServer` och `trackingServerSecure` har angetts.

Om din organisation fortfarande behöver den här variabeln väljer du ett värde som representerar din organisation. Du kan lagra det här värdet i ett [lösningsdesigndokument](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
