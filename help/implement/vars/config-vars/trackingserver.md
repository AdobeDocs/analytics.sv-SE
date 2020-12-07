---
title: trackingServer
description: Ange vilken plats bildbegäranden ska skickas till.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 1%

---


# trackingServer

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. Variabeln avgör `trackingServer` var en bildbegäran skickas. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!IMPORTANT]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Spårningsserver i Adobe Experience Platform Launch

Spårningsservern är ett fält under [!UICONTROL General] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL General] [!UICONTROL Tracking Server] fältet.

Om fältet lämnas tomt blir det som standard `[rsid]sc.adobedc.net`.

## s.trackingServer i AppMeasurement och Launch, anpassad kodredigerare

Variabeln `s.trackingServer` är en sträng som innehåller platsen där data ska skickas.

>[!TIP]
>
>Vissa implementeringar pekar på data `2o7.net`. Även om detta är en giltig datainsamlingsdomän används inte regional datainsamling. Implementeringar som använder en något högre svarstid för bildbegäran `2o7.net` visas.

## Bestämma värdet för trackingServer

Värdet för den här variabeln beror på om du använder cookies från första part eller cookies från tredje part. Adobe rekommenderar starkt att du använder cookies från första part i implementeringen.

### cookies från första part

Om du använder en cookie-implementering från en annan tillverkare är det troligt att någon i din organisation redan har slutfört cookie-processen från första part. Mer information om cookie-processen finns i [cookies från första part i Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna.

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

Din organisation kanske redan använder en spårningsserver från tredje part i `sc.adobedc.net` - eller `2o7.net` -domänerna.  Dessa användes huvudsakligen i tidigare versioner av Adobe Analytics och är fortfarande giltiga.

>[!NOTE]
>
>Använd inte underdomäner djupare än `example.data.adobedc.net`. Detta `custom.example.data.adobedc.net` är till exempel inte en giltig spårningsserver.
