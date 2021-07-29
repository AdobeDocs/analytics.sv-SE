---
title: visitorNameSpace
description: En indragen variabel som fastställde cookie-domän.
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# visitorNamespace

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) i stället.

I tidigare versioner av Adobe Analytics använde AppMeasurement variabeln `visitorNameSpace` för att avgöra underdomänen `2o7.net` där besökares cookies lagras. Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. I och med introduktionen av variablerna `trackingServer` och [`trackingServerSecure`](trackingserversecure.md) behövs inte längre `visitorNameSpace`.

>[!TIP]
>
>Adobe rekommenderar att du använder cookies från första part på din webbplats. Den här variabeln används inte för cookies från första part.

## Namnutrymme för besökare med hjälp av taggar i Adobe Experience Platform

[!UICONTROL Visitor Namespace] är ett fält under  [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Cookies], som visar fältet [!UICONTROL Visitor Namespace].

Adobe avråder från att använda det här fältet. Använd `trackingServer` och `trackingServerSecure` i stället.

## s.visitorNamespace i AppMeasurement och anpassad kodredigerare

Variabeln `s.visitorNamespace` är en sträng som innehåller ett unikt värde per organisation. Gamla AppMeasurement-bibliotek har automatiskt inkluderat detta unika värde när de laddas ned från tidigare versioner av Adobe Analytics. Aktuella AppMeasurement-bibliotek använder inte den här variabeln såvida inte `trackingServer` och `trackingServerSecure` inte har angetts.

Om din organisation fortfarande behöver den här variabeln väljer du ett värde som representerar din organisation. Du kan lagra det här värdet i ett [lösningsdesigndokument](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
