---
title: useBeacon
description: Med useBeacon kan du tvinga AppMeasurement att använda webbläsarnas sendBeacon-API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# useBeacon

De flesta moderna webbläsare har den inbyggda metoden `navigator.sendBeacon()`. Den skickar asynkront en liten mängd data via HTTP till en webbserver. AppMeasurement kan använda `navigator.sendBeacon()` metoden om `useBeacon` variabeln är aktiverad. Det är användbart för att avsluta länkar och andra situationer där du vill skicka information innan sidan tas bort.

If `useBeacon` är aktiverat, nästa träff som skickas till Adobe använder webbläsarens `navigator.sendBeacon()` i stället för en standard `GET` bildförfrågan. Den här variabeln gäller för båda [`s.t()`](../functions/t-method.md) och [`s.tl()`](../functions/tl-method.md) bildbegäranden. AppMeasurement 2.17.0 eller senare krävs.

>[!TIP]
>
>AppMeasurement aktiverar automatiskt `useBeacon` för att avsluta länkbildsförfrågningar.

The `useBeacon` variabeln ignoreras när besökaren använder en webbläsare som inte stöder `navigator.sendBeacon()`. Användning av den här variabeln kräver AppMeasurement 2.16.0 eller senare.

## Använda API:t sendBeacon med Web SDK-tillägget

The **[!UICONTROL Document will unload]** kryssrutan i en åtgärdskonfiguration avgör om data som skickas till Adobe använder API:t sendBeacon.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel.
1. Under [!UICONTROL Actions]klickar du på funktionsmakrot eller klickar på **&#39;+&#39;** om du vill lägga till ett nytt funktionsmakro.
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

Se [Använda API:t sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) i Web SDK-dokumentationen om du vill ha mer information.

## Använd Beacon med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.useBeacon i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.useBeacon` är en boolesk variabel som avgör om AppMeasurement använder webbläsarens `navigator.sendBeacon()` -metod. Standardvärdet är `false`. Ange variabeln till `true` innan du anropar en spårningsfunktion om du vill använda den asynkrona typen av `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>När ett spårningsanrop har körts återställs variabeln till `false`. Om implementeringen skickar flera bildbegäranden i samma sidinläsning (t.ex. enkelsidiga program), ställer du in den här variabeln på `true` före varje spårningsanrop.
