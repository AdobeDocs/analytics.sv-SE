---
title: trackingServer
description: Ange vilken plats bildbegäranden ska skickas till.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 1%

---

# trackingServer

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. The `trackingServer` variabeln bestämmer var en bildbegäran skickas. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!WARNING]
>
>Om du ändrar det här värdet får AppMeasurement att söka efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Edge domain using the Web SDK extension

Web SDK använder [!UICONTROL Edge domain] för att hantera både spårningsserver och server för säker spårning. Du kan ställa in önskat [!UICONTROL Edge domain] när du konfigurerar Web SDK-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange önskat **[!UICONTROL Edge domain]** textfält.

Se [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) i Web SDK-dokumentationen om du vill ha mer information.

>[!TIP]
>
>Om organisationen går över till Web SDK från en AppMeasurement- eller Analytics-tilläggsimplementering kan det här fältet använda samma värde som i `trackingServerSecure` (eller `trackingServer`).

## Edge domain implementerar Web SDK manuellt

Konfigurera SDK med [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html). Fältet är en sträng som avgör vilken domän som data ska skickas till.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Spårningsserver med Adobe Analytics-tillägget

Spårningsservern är ett fält under [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL Tracking Server] fält.

Om fältet lämnas tomt blir standardvärdet `[rsid].data.adobedc.net`.

## s.trackingServer i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.trackingServer` variabeln är en sträng som innehåller platsen där data ska skickas.

## Bestäm värdet för `trackingServer`

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
