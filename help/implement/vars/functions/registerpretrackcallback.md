---
title: registerPreTrackCallback
description: Skapa callback-funktioner innan du skickar en träff till Adobe.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

Variabeln gör att din organisation kan koppla en JavaScript-funktion efter att en URL för bildbegäran har kompilerats, men innan den skickas. `registerPreTrackCallback` Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur.

> [!IMPORTANT] Anropa inga spårningsfunktioner som `t` eller `tl` inuti `registerPostTrackCallback` variabeln. Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du anropar `registerPreTrackCallback` variabeln kopplar du den funktionen till körning varje gång en URL för bildbegäran kompileras. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

> [!NOTE] Tidpunkten och ordningen för funktioner som utlöses mellan `registerPreTrackCallback` och `registerPostTrackCallback` är inte säkerställda. Undvik beroenden mellan dessa två funktioner.

## Registrera Pre Track-återanrop i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPreTrackCallback i AppMeasurement and Launch custom code editor

Funktionen `s.registerPreTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs precis innan en bildbegäran skickas.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet i den kapslade funktionen `requestUrl` . Du kan tolka variabeln för den användning du vill använda; `requestUrl` om du justerar den här variabeln påverkas inte datainsamlingen.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ytterligare argument kan inkluderas i `s.registerPreTrackCallback` funktionen, som kan användas i den kapslade funktionen:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] Om du anger sidvariabler eller ändrar `requestUrl` strängen i den här funktionen påverkas *inte* bildbegäran som skickas kort efter det här funktionsanropet.
