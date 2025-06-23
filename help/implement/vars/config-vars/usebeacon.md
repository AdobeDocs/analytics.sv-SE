---
title: useBeacon
description: Med useBeacon kan du tvinga AppMeasurement att använda webbläsarnas sendBeacon API
feature: Appmeasurement Implementation
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# useBeacon

De flesta moderna webbläsare innehåller den inbyggda metoden `navigator.sendBeacon()`. Den skickar asynkront en liten mängd data via HTTP till en webbserver. AppMeasurement kan använda metoden `navigator.sendBeacon()` om variabeln `useBeacon` är aktiverad. Det är användbart för att avsluta länkar och andra situationer där du vill skicka information innan sidan tas bort.

Om `useBeacon` är aktiverat använder nästa träff som skickas till Adobe webbläsarens `navigator.sendBeacon()`-metod i stället för en standardbildbegäran för `GET`. Den här variabeln gäller för både [`s.t()`](../functions/t-method.md)- och [`s.tl()`](../functions/tl-method.md)-bildbegäranden. AppMeasurement 2.17.0 eller senare krävs.

>[!TIP]
>
>AppMeasurement aktiverar automatiskt `useBeacon` för att avsluta länkbildsbegäranden.

Variabeln `useBeacon` ignoreras när besökaren använder en webbläsare som inte stöder `navigator.sendBeacon()`. Om du vill använda den här variabeln måste du ha AppMeasurement 2.16.0 eller senare.

## Använda API:t sendBeacon med Web SDK-tillägget

Kryssrutan **[!UICONTROL Document will unload]** i en åtgärdskonfiguration avgör om data som skickas till Adobe använder API:t sendBeacon.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel.
1. Klicka på önskad åtgärd under [!UICONTROL Actions] eller klicka på ikonen **+** för att lägga till en ny åtgärd.
1. Ställ in listrutan [!UICONTROL Extension] till **[!UICONTROL Adobe Experience Platform Web SDK]** och [!UICONTROL Action Type] till **[!UICONTROL Send event]**
1. Klicka i kryssrutan **[!UICONTROL Document will unload]** till höger.

Om den här rutan är markerad skickas data till Adobe med API:t sendBeacon. Den är avmarkerad som standard.

## Använda API:t sendBeacon för att implementera Web SDK manuellt

Ange `documentUnloading` till `true` när du skickar en händelse. Om den inte anges är standardvärdet `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Mer information finns i [Använda API:t sendBeacon ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#using-the-sendbeacon-api) i dokumentationen för Web SDK.

## Använd Beacon med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.useBeacon i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.useBeacon` är en boolesk variabel som avgör om AppMeasurement använder webbläsarens `navigator.sendBeacon()`-metod. Dess standardvärde är `false`. Ange variabeln till `true` innan du anropar en spårningsfunktion om du vill använda den asynkrona typen `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>När ett spårningsanrop körs återställs variabeln till `false`. Om implementeringen skickar flera bildbegäranden i samma sidinläsning (till exempel enkelsidiga program), ställer du in variabeln på `true` före varje spårningsanrop.
