---
title: registerPreTrackCallback
description: Skapa callback-funktioner innan du skickar en träff till Adobe.
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# registerPreTrackCallback

Variabeln `registerPreTrackCallback` gör att din organisation kan koppla en JavaScript-funktion efter att en URL för bildbegäran har kompilerats, men innan den skickas. Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur.

>[!IMPORTANT]
>
>Anropa inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti variabeln [`registerPostTrackCallback`](registerposttrackcallback.md). Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du anropar variabeln `registerPreTrackCallback` kopplar du den funktionen till körning varje gång en URL för bildbegäran kompileras. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidsangivelsen och ordningen för funktioner som utlösts mellan `registerPreTrackCallback` och `registerPostTrackCallback` är inte garanterad. Undvik beroenden mellan dessa två funktioner.

## Registrera Pre Track-återanrop med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPreTrackCallback i AppMeasurement och anpassad kodredigerare

`s.registerPreTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs precis innan en bildbegäran skickas.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet `requestUrl` i den kapslade funktionen. Du kan analysera variabeln `requestUrl` för att kunna använda den. om du justerar den här variabeln påverkas inte datainsamlingen.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Du kan inkludera ytterligare argument i funktionen `s.registerPreTrackCallback`, som kan användas i den kapslade funktionen:

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
>Om du anger sidvariabler eller ändrar strängen `requestUrl` i den här funktionen påverkar det inte **bildbegäran som skickas kort efter det här funktionsanropet.** Använd variabeln [`doPlugins()`](doplugins.md) i stället.
