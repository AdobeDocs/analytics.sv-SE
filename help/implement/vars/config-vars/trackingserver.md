---
title: trackingServer
description: Ange vilken plats bildbegäranden ska skickas till.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---

# trackingServer

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. The `trackingServer` variabeln bestämmer var en bildbegäran skickas. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!WARNING]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Spåra server med hjälp av taggar i Adobe Experience Platform

Spårningsservern är ett fält under [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL Tracking Server] fält.

Om fältet lämnas tomt blir standardvärdet `[rsid].data.adobedc.net`.

## s.trackingServer i AppMeasurement och anpassad kodredigerare

The `s.trackingServer` variabeln är en sträng som innehåller platsen där data ska skickas.

## Bestämma värdet för trackingServer

Värdet för den här variabeln beror på om du använder cookies från första part eller cookies från tredje part. Adobe rekommenderar starkt att du använder cookies från första part i implementeringen.

### cookies från första part

Om du använder en cookie-implementering från en annan tillverkare är det troligt att någon i din organisation redan har slutfört cookie-processen från första part. Se [Första parts-cookies i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna för mer information om cookie-processen från första part.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServer = "data.example.com";
```

### cookies från tredje part

>[!TIP]
>
>Ökad sekretesspraxis i moderna webbläsare gör cookies från tredje part mindre tillförlitliga. Adobe rekommenderar att du följer arbetsflödet för cookies från första part.

Om du använder en cookie-implementering från en annan leverantör, är värdet för `trackingServer` är en underdomän till `data.adobedc.net`. Exempel:

```js
s.trackingServer = "example.data.adobedc.net";
```

Välj en underdomän som är unik för din organisation och som sannolikt inte plockas av någon annan organisation som använder Adobe Analytics.  Vi rekommenderar att besökarens namnutrymme tilldelas din organisation.  Se till att alla implementeringar i organisationen använder samma spårningsserver. Det kan vara praktiskt att behålla informationen i en [konstruktionsdokument](../../prepare/solution-design.md).

Din organisation kanske redan använder en spårningsserver från tredje part i `sc.omtrdc.net` eller `2o7.net` domäner.  Dessa användes huvudsakligen i tidigare versioner av Adobe Analytics och är fortfarande giltiga.

>[!NOTE]
>
>Använd inte underdomäner djupare än `example.data.adobedc.net`. Till exempel: `custom.example.data.adobedc.net` är inte en giltig spårningsserver.
