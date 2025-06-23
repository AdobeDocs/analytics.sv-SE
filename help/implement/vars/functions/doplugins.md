---
title: doPlugins
description: Konfigurera logik precis innan en träff kompileras och skickas till Adobe.
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# doPlugins

Variabeln `doPlugins` fungerar som ett&quot;sista anrop&quot; för att ange värden i implementeringen. Det är en idealisk plats att anropa [plug-in-metoder](../plugins/impl-plugins.md) och ange önskade variabler innan en bildbegäran skickas. Om [`usePlugins`](../config-vars/useplugins.md) är aktiverat körs den automatiskt precis innan någon typ av bildbegäran kompileras och skickas till Adobe, inklusive:

* Alla sidvyanrop ([`t()`](t-method.md))
* Alla länkspårningsanrop ([`tl()`](tl-method.md)), inklusive automatiska hämtningslänkar och avslutningslänkar

Använd variabeln `doPlugins` för att anropa plugin-programkod och ange slutliga variabelvärden precis innan en bildbegäran kompileras och skickas till Adobe.

## Använda On Before Event Skicka callback-kod med tillägget Web SDK

I stället för `doPlugins` använder Web SDK `onBeforeEventSend` med liknande funktioner.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Klicka på knappen **[!UICONTROL Edit on before event send callback code]** under [!UICONTROL Data Collection].
1. Placera önskad kod i redigeraren.

## Använd `onBeforeEventSend` för att implementera Web SDK manuellt

I stället för `doPlugins` använder Web SDK `onBeforeEventSend` med liknande funktioner. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#modifying-events-globally) i Web SDK-dokumentationen.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plugin-program som använder tillägget Adobe Analytics

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.doPlugins i AppMeasurement och anpassad kod

Ange variabeln `s.doPlugins` till en funktion som innehåller önskad kod. Funktionen körs automatiskt när du anropar spårning.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Ange en funktion för variabeln `doPlugins` endast en gång i implementeringen. Om du anger variabeln `doPlugins` mer än en gång används bara den senaste koden.

## Exempel

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Tidigare versioner av AppMeasurement hade något annorlunda `doPlugins()`-kod. Adobe rekommenderar att du använder ovanstående format som en god vana.
