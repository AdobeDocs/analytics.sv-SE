---
title: registerPreTrackCallback
description: Skapa callback-funktioner innan du skickar en träff till Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# registerPreTrackCallback

The `registerPreTrackCallback` kan din organisation koppla en JavaScript-funktion efter att en URL för bildbegäran har kompilerats, men innan den skickas. Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur.

>[!WARNING]
>
>Anropa inga spårningssamtal som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti [`registerPostTrackCallback`](registerposttrackcallback.md) variabel. Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du ringer `registerPreTrackCallback` kan du koppla den funktionen till körning varje gång en URL för bildbegäran kompileras. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidpunkt och ordning för de funktioner som utlöses mellan `registerPreTrackCallback` och `registerPostTrackCallback` är inte garanterade. Undvik beroenden mellan dessa två funktioner.

## Registrera Pre Track-återanrop med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPreTrackCallback i AppMeasurement och anpassad kodredigerare

The `s.registerPreTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs precis innan en bildbegäran skickas.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden ska du referera till `requestUrl` strängargument i den kapslade funktionen. Du kan analysera `requestUrl` variabel för det du vill använda, om du justerar den här variabeln påverkas inte datainsamlingen.

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
