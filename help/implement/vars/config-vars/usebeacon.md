---
title: useBeacon
description: useBeacon gör att du kan tvinga AppMeasurementet att använda webbläsarens sendBeacon-API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# useBeacon

I de flesta moderna webbläsare finns den inbyggda metoden `navigator.sendBeacon()`. Den skickar asynkront en liten mängd data via HTTP till en webbserver. AppMeasurementet kan använda `navigator.sendBeacon()` metoden om `useBeacon` variabeln är aktiverad. Det är användbart för att avsluta länkar och andra situationer där du vill skicka information innan sidan tas bort.

If `useBeacon` är aktiverat, nästa träff som skickas till Adobe använder webbläsarens `navigator.sendBeacon()` metod i stället för en standard `GET` bildförfrågan. Den här variabeln gäller för båda [`s.t()`](../functions/t-method.md) och [`s.tl()`](../functions/tl-method.md) bildbegäranden. AppMeasurement 2.17.0 eller senare krävs.

>[!TIP]
>
>AppMeasurementet aktiveras automatiskt `useBeacon` för att avsluta länkbildsförfrågningar.

The `useBeacon` variabeln ignoreras när besökaren använder en webbläsare som inte stöder `navigator.sendBeacon()`. Om du vill använda den här variabeln måste du ha AppMeasurementet 2.16.0 eller senare.

## Använda API:t sendBeacon med Web SDK-tillägget

The **[!UICONTROL Document will unload]** kryssrutan i en åtgärdskonfiguration avgör om data som skickas till Adobe använder API:t sendBeacon.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel.
1. Under [!UICONTROL Actions]klickar du på funktionsmakrot eller klickar på **&#39;+&#39;** om du vill lägga till en ny åtgärd.
1. Ange [!UICONTROL Extension] nedrullningsbar lista till **[!UICONTROL Adobe Experience Platform Web SDK]** och [!UICONTROL Action Type] till **[!UICONTROL Send event]**
1. Klicka i kryssrutan **[!UICONTROL Document will unload]** till höger.

Om den här rutan är markerad skickas data till Adobe med API:t sendBeacon. Den är avmarkerad som standard.

## Använda API:t sendBeacon för att implementera Web SDK manuellt

Ange `documentUnloading` till `true` när en händelse skickas. Om den inte anges är standardvärdet `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Se [Använda API:t sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) finns i Web SDK-dokumentationen.

## Använd Beacon med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.useBeacon i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.useBeacon` är en boolesk variabel som avgör om AppMeasurementet använder webbläsarens `navigator.sendBeacon()` -metod. Standardvärdet är `false`. Ange variabeln till `true` innan du anropar en spårningsfunktion om du vill använda den asynkrona typen av `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>När ett spårningsanrop körs återställs variabeln till `false`. Om implementeringen skickar flera bildbegäranden i samma sidinläsning (t.ex. enkelsidiga program), ställer du in den här variabeln på `true` före varje spårningsanrop.
