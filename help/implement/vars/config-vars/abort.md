---
title: avbryta
description: Variabeln abort är en boolesk variabel som förhindrar att en träff skickas till datainsamlingsservrar i Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# avbryta

The `abort` är en boolesk variabel som kan förhindra att nästa spårningsanrop skickas till Adobe. Liknande funktioner finns i Web SDK, som gör att du kan returnera `false` innan en XDM-händelse skickas.

## Avbryt sändning av en händelse med Web SDK-tillägget

Använd [!UICONTROL On before event send callback] kodredigerare och returnera `false`.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection]klickar du på **[!UICONTROL Edit on before event send callback code]** -knappen.
1. I kodredigeraren placerar du följande kod under de förhållanden som du vill avbryta när du skickar data till Edge:

```js
return false;
```

## Avbryt sändning av en händelse som implementerar Web SDK manuellt

Använd `onBeforeEventSend` callback och return `false`. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) finns i Web SDK-dokumentationen.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Använda variabeln abort i Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.abort in AppMeasurement and the Analytics extension custom code editor

The `s.abort` är en boolesk variabel. Standardvärdet är `false`.

* Om inställt på `true`, nästa spårningsanrop ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)) skickar inga data till Adobe.
* Om inställt på `false` eller inte är definierad gör den här variabeln ingenting.

```js
s.abort = true;
```

>[!NOTE]
>
>The `abort` variabeln återställs till `false` efter varje spårningssamtal. Om du vill avbryta efterföljande spårningsanrop på samma sida anger du `abort` till `true` igen.

The `abort` variabeln kan anges i [`doPlugins()`](../functions/doplugins.md) -funktion, som är den sista funktionen som körs innan en bildbegäran skickas till Adobe. Det här exemplet fungerar ungefär som `onBeforeEventSend` återanrop med Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Du kan centralisera den logik som du använder för att identifiera aktiviteter som du inte vill spåra, till exempel vissa anpassade länkar eller externa länkar i visningsannonser.
