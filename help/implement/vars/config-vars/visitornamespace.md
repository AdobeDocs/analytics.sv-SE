---
title: visitorNameSpace
description: En indragen variabel som fastställde cookie-domän.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorNamespace

> [!IMPORTANT] Den här variabeln har tagits bort. Använd `trackingServer` istället.

I tidigare versioner av Adobe Analytics använde AppMeasurement variabeln för att avgöra vilken underdomän `visitorNameSpace` `2o7.net` besökarens cookies lagras i. Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. I och med introduktionen av variablerna `trackingServer` och `trackingServerSecure` behövs `visitorNameSpace` inte längre.

> [!TIP] Adobe rekommenderar att du använder cookies från första part på din webbplats. Den här variabeln används inte för cookies från första part.

## Namnutrymme för besökare i Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] är ett fält under [!UICONTROL Cookies] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Cookies] [!UICONTROL Visitor Namespace] fältet.

Adobe rekommenderar att du inte använder det här fältet. Använd `trackingServer` och `trackingServerSecure` istället.

## s.visitorNamespace i AppMeasurement and Launch custom code editor

Variabeln `s.visitorNamespace` är en sträng som innehåller ett unikt värde per organisation. Gamla AppMeasurement-bibliotek inkluderade automatiskt detta unika värde när de laddades ned från tidigare versioner av Adobe Analytics. Aktuella AppMeasurement-bibliotek använder inte den här variabeln om `trackingServer` och `trackingServerSecure` inte har angetts.

Om din organisation fortfarande behöver den här variabeln väljer du ett värde som representerar din organisation. Du kan lagra det här värdet i ett [lösningsdesigndokument](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
