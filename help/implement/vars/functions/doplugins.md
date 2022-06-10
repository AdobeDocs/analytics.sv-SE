---
title: doPlugins
description: Konfigurera logik precis innan en träff kompileras och skickas till Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# doPlugins

The `doPlugins` variabeln fungerar som ett&quot;sista anrop&quot; för att ange värden i implementeringen. If [`usePlugins`](../config-vars/useplugins.md) är aktiverat körs den automatiskt precis innan någon typ av bildbegäran kompileras och skickas till Adobe, inklusive:

* All sidvy ([`t()`](t-method.md)) samtal
* All länkspårning ([`tl()`](tl-method.md)), inklusive automatiska nedladdningslänkar och avslutningslänkar

Använd `doPlugins` variabel för att anropa plugin-kod och ange slutliga variabelvärden precis innan en bildbegäran kompileras och skickas till Adobe.

## Använd On Before Event Skicka callback-kod med Web SDK-tillägget

I stället för `doPlugins`används `onBeforeEventSend` med liknande funktionalitet.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection]klickar du på **[!UICONTROL Edit on before event send callback code]** -knappen.
1. Placera önskad kod i redigeraren.

## Använd `onBeforeEventSend` implementera Web SDK manuellt

I stället för `doPlugins`används `onBeforeEventSend` med liknande funktionalitet. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) i Web SDK-dokumentationen om du vill ha mer information.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plugin-program som använder tillägget Adobe Analytics

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.doPlugins in AppMeasurement and custom code

Ange `s.doPlugins` till en funktion som innehåller önskad kod. Funktionen körs automatiskt när du gör ett spårningsanrop.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Ange en funktion för `doPlugins` endast en gång i implementeringen. Om du anger `doPlugins` variabel mer än en gång, används bara den senaste koden.

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
>Tidigare versioner av AppMeasurement hade något annorlunda `doPlugins()` kod. Adobe rekommenderar att du använder formatet ovan som en god praxis.
