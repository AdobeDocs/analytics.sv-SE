---
title: avbryta
description: Variabeln abort är en boolesk variabel som förhindrar att en träff skickas till Adobe datainsamlingsservrar.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# avbryta

Variabeln `abort` är en boolesk variabel som kan förhindra att nästa spårningsanrop skickas till Adobe. Det finns liknande funktioner i Web SDK som gör att du kan returnera `false` innan en XDM-händelse skickas.

## Avbryt sändning av en händelse med tillägget Web SDK

Använd kodredigeraren [!UICONTROL On before event send callback] och returnera `false`.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Klicka på knappen **[!UICONTROL Edit on before event send callback code]** under [!UICONTROL Data Collection].
1. I kodredigeraren placerar du följande kod under de förhållanden som du vill avbryta när du skickar data till Edge:

```js
return false;
```

## Avbryta sändning av en händelse manuellt som implementerar Web SDK

Använd motringningen `onBeforeEventSend` och returnera `false`. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#modifying-events-globally) i Web SDK-dokumentationen.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Använda variabeln abort i Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.abort in AppMeasurement and the Analytics extension custom code editor

Variabeln `s.abort` är boolesk. Dess standardvärde är `false`.

* Om värdet är `true` skickas inga data till Adobe vid nästa spårningsanrop ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)).
* Om värdet är `false` eller inte definierat händer ingenting.

```js
s.abort = true;
```

>[!NOTE]
>
>Variabeln `abort` återställs till `false` efter varje spårningsanrop. Om du vill avbryta efterföljande spårningsanrop på samma sida anger du `abort` till `true` igen.

Variabeln `abort` kan anges i funktionen [`doPlugins()`](../functions/doplugins.md) som är den sista funktionen som körs innan en bildbegäran skickas till Adobe. Det här exemplet fungerar på ungefär samma sätt som `onBeforeEventSend`-återanropet med Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Du kan centralisera den logik som du använder för att identifiera aktiviteter som du inte vill spåra, till exempel vissa anpassade länkar eller externa länkar i visningsannonser.
