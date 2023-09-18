---
title: registerPreTrackCallback
description: Skapa callback-funktioner innan du skickar en träff till Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# registerPreTrackCallback

The `registerPreTrackCallback` kan din organisation koppla en JavaScript-funktion efter att en URL för bildbegäran har kompilerats, men innan den skickas. Du kan använda den här variabeln för att skicka data som samlats in av AppMeasurementet till en partner eller intern infrastruktur.

>[!WARNING]
>
>Gör inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) innanför `registerPreTrackCallback` variabel. Om du anger spårningsanrop i den här variabeln skapas en oändlig slinga med bildbegäranden!

Varje gång du ringer `registerPreTrackCallback` kan du koppla den funktionen till körning varje gång en URL för bildbegäran kompileras. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidpunkt och ordning för de funktioner som utlöses mellan `registerPreTrackCallback` och `registerPostTrackCallback` är inte garanterade. Undvik beroenden mellan dessa två funktioner.

## Förspåra återanrop med Web SDK-tillägget

Web SDK kan inte koppla en funktion efter att data har kompilerats, men innan den skickas till Adobe. Du kan dock använda `onBeforeEventSend` för att registrera en funktion som ska köras precis innan data skickas.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Användargränssnitt som använder dina AdobeID-autentiseringsuppgifter.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection]klickar du på **[!UICONTROL Edit on before event send callback code]** -knappen.
1. Placera önskad kod i redigeraren.

## Förspåra återanrop manuellt genom att implementera Web SDK

Web SDK kan inte koppla en funktion efter att data har kompilerats, men innan den skickas till Adobe. Du kan dock använda `onBeforeEventSend` för att registrera en funktion som ska köras precis innan data skickas, ungefär som `doPlugins`. Se [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) finns i Web SDK-dokumentationen.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Förspåra återanrop med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.registerPreTrackCallback i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.registerPreTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs precis innan en bildbegäran skickas.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden ska du referera till `requestUrl` strängargument i den kapslade funktionen. Du kan analysera `requestUrl` -variabel för det du vill använda. Om du justerar den här variabeln påverkas inte datainsamlingen.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Du kan inkludera ytterligare argument i `s.registerPreTrackCallback` som kan användas i den kapslade funktionen:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>Ställa in sidvariabler eller ändra `requestUrl` strängen i den här funktionen gör **not** påverkar bildbegäran som skickas kort efter det här funktionsanropet. Använd [`doPlugins()`](doplugins.md) i stället.
