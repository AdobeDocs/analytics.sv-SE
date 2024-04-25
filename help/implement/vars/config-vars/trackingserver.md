---
title: trackingServer
description: Ange vilken plats bildbegäranden ska skickas till.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 284f121428ce9d682b42309dd85cfd117285a7e5
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---

# trackingServer

Adobe samlar in data på er webbplats genom att ta emot en bildförfrågan som genererats av besökaren. The `trackingServer` variabeln bestämmer var en bildbegäran skickas. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

>[!WARNING]
>
>Om du ändrar det här värdet söker AppMeasurementet efter cookies på en annan plats. Unikt besökarantal kan tillfälligt öka i rapporteringen när besökarcookies anges på den nya platsen.

## Edge domain using the Web SDK extension

Web SDK använder [!UICONTROL Edge domain] för att hantera både spårningsserver och server för säker spårning. Du kan ställa in önskat [!UICONTROL Edge domain] när du konfigurerar Web SDK-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange önskat **[!UICONTROL Edge domain]** textfält.

Se [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) finns i Web SDK-dokumentationen.

>[!TIP]
>
>Om din organisation går över till Web SDK från en implementering av ett AppMeasurement- eller Analytics-tillägg kan det här fältet använda samma värde som i `trackingServerSecure` (eller `trackingServer`).

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

## s.trackingServer i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.trackingServer` variabeln är en sträng som innehåller platsen där data ska skickas.

## Att tänka på vid bestämning av värdet för `trackingServer`

Du kan välja att använda Adobe spårningsserverdomäner (t.ex. `adobedc.net`) eller du kan gå igenom en särskild process för att konfigurera en spårningsserver som matchar din webbplatsdomän (t.ex. `data.mydomain.com`), även känd som en CNAME-implementering. En spårningsserver som matchar din webbplatsdomän kan ha vissa fördelar beroende på andra aspekter av implementeringen. Om spårningsservern inte matchar domänen för den aktuella sidan måste cookies som anges av AppMeasurementet anges som tredjepartsserver. Om webbläsaren inte stöder cookies från tredje part kan den här felmatchningen påverka vissa analysfunktioner:

- Inställning av identifierare: Om du använder Experience Cloud Identity Service har spårningsservern ingen effekt på hur cookies anges. Men om du använder äldre Analytics-identifierare (även `s_vi` cookie) och samlingsservern inte matchar den aktuella domänen, måste cookies anges som tredje part. I det här fallet, om cookies från tredje part blockeras av webbläsaren, ställer Analytics in ett reservations-ID (`s_fid`) istället för standarden `s_vi` cookie.
- Länkspårning fungerar inte för interna länkar.
- Activity Map fungerar inte för interna länkar.
- Cookie-check.

### cookies från första part

Om du använder en cookie-implementering från en annan tillverkare är det troligt att någon i din organisation redan har slutfört cookie-processen från första part. Se [Första parts-cookies i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) i användarhandboken för bastjänsterna för mer information om cookie-processen från första part.

Den person som initialt konfigurerar cookie-implementeringen från första part definierar också den domän och underdomän som används. Exempel:

```js
s.trackingServer = "data.example.com";
```

### Spårningsserver från tredje part

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
