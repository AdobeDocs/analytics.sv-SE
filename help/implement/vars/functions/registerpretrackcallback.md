---
title: registerPreTrackCallback
description: Skapa callback-funktioner innan du skickar en träff till Adobe.
feature: Appmeasurement Implementation
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---

# registerPreTrackCallback

Variabeln `registerPreTrackCallback` gör att din organisation kan koppla en JavaScript-funktion efter att en URL för bildbegäran har kompilerats, men innan den skickas. Du kan använda den här variabeln för att skicka data som samlats in av AppMeasurement till en partner eller intern infrastruktur.

>[!WARNING]
>
>Gör inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti variabeln `registerPreTrackCallback`. Om du anger spårningsanrop i den här variabeln skapas en oändlig slinga med bildbegäranden!

Varje gång du anropar variabeln `registerPreTrackCallback` kopplar du den funktionen till körning varje gång en URL för bildbegäran kompileras. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidsangivelsen och ordningen för funktioner som utlösts mellan `registerPreTrackCallback` och `registerPostTrackCallback` garanteras inte. Undvik beroenden mellan dessa två funktioner.

## Förspåra återanrop med Web SDK-tillägget

SDK kan inte koppla en funktion när data har kompilerats, men innan den skickas till Adobe. Du kan dock använda `onBeforeEventSend` för att registrera en funktion som ska köras precis innan data skickas.

1. Logga in på användargränssnittet för [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Klicka på knappen **[!UICONTROL Edit on before event send callback code]** under [!UICONTROL Data Collection].
1. Placera önskad kod i redigeraren.

## Förspåra återanrop manuellt för att implementera Web SDK

SDK kan inte koppla en funktion när data har kompilerats, men innan den skickas till Adobe. Du kan emellertid använda `onBeforeEventSend` för att registrera en funktion som ska köras precis innan data skickas, ungefär som `doPlugins`. Mer information finns i [Ändra händelser globalt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#modifying-events-globally) i Web SDK-dokumentationen.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Förspåra återanrop med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.registerPreTrackCallback i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

`s.registerPreTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs precis innan en bildbegäran skickas.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet `requestUrl` i den kapslade funktionen. Du kan tolka variabeln `requestUrl` om du vill använda den. Om du justerar variabeln påverkas inte datainsamlingen.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Du kan inkludera ytterligare argument i funktionen `s.registerPreTrackCallback` som kan användas i den kapslade funktionen:

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
>Om du anger sidvariabler eller ändrar strängen `requestUrl` i den här funktionen påverkas **inte** bildbegäran som skickas kort efter det här funktionsanropet. Använd variabeln [`doPlugins()`](doplugins.md) i stället.
