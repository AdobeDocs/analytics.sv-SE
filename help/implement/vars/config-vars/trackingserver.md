---
title: trackingServer
description: Ange vilken plats bildbegäranden ska skickas till.
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# trackingServer

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. Variabeln `trackingServer` avgör var en bildbegäran skickas. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!IMPORTANT]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Spårningsserver i Adobe Experience Platform Launch

Spårningsservern är ett fält under dragspelet [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL General], som visar fältet [!UICONTROL Tracking Server].

Om fältet lämnas tomt är det som standard `[rsid].data.adobedc.net`.

## s.trackingServer i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.trackingServer` är en sträng som innehåller platsen där data ska skickas.

## Bestämma värdet för trackingServer

Värdet för den här variabeln beror på om du använder cookies från första part eller cookies från tredje part. Adobe rekommenderar starkt att du använder cookies från första part i implementeringen.

### cookies från första part

Om du använder en cookie-implementering från en annan tillverkare är det troligt att någon i din organisation redan har slutfört cookie-processen från första part. Se [cookies från första part i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna för mer information om cookie-processen från första part.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServer = "data.example.com";
```

### cookies från tredje part

>[!TIP]
>
>Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. Adobe rekommenderar att du följer arbetsflödet för cookies från första part.

Om du använder en cookie-implementering från tredje part är värdet för `trackingServer` en underdomän till `data.adobedc.net`. Exempel:

```js
s.trackingServer = "example.data.adobedc.net";
```

Välj en underdomän som är unik för din organisation och som sannolikt inte plockas av någon annan organisation som använder Adobe Analytics.  Vi rekommenderar att besökarens namnutrymme tilldelas din organisation.  Se till att alla implementeringar i organisationen använder samma spårningsserver. Det kan vara praktiskt att behålla denna information i ett [lösningsdesigndokument](../../prepare/solution-design.md).

Din organisation kanske redan använder en spårningsserver från tredje part i domänerna `sc.omtrdc.net` eller `2o7.net`.  Dessa användes huvudsakligen i tidigare versioner av Adobe Analytics och är fortfarande giltiga.

>[!NOTE]
>
>Använd inga underdomäner djupare än `example.data.adobedc.net`. `custom.example.data.adobedc.net` är till exempel inte en giltig spårningsserver.
