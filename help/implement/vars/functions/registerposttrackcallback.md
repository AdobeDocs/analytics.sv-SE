---
title: registerPostTrackCallback
description: Skapa callback-funktioner när du har skickat en träff till Adobe.
translation-type: tm+mt
source-git-commit: 0d7e7dcb2cc382d83e267e51b1abeff38da270d3
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# registerPostTrackCallback

Variabeln gör att din organisation kan koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. `registerPostTrackCallback` Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!IMPORTANT] Anropa inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti `registerPostTrackCallback` variabeln. Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du anropar `registerPostTrackCallback` variabeln, kopplar du den funktionen till körning omedelbart efter att en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE] Tidpunkten och ordningen för funktioner som utlöses mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` är inte säkerställda. Undvik beroenden mellan dessa två funktioner.

## Registrera återanrop efter spår i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPostTrackCallback i AppMeasurement and Launch custom code editor

Funktionen `s.registerPostTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs omedelbart när en bildbegäran har skickats.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet i den kapslade funktionen `requestUrl` . Du kan tolka variabeln för den användning du vill använda; `requestUrl` om du justerar den här variabeln påverkas inte datainsamlingen.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ytterligare argument kan inkluderas i `s.registerPostTrackCallback` funktionen, som kan användas i den kapslade funktionen:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Exempel på användningsfall

Det kan vara bra att registrera [`clearVars()`](clearvars.md) funktionen i efterspårets återanrop för enkelsidiga program. Varje gång du skickar en träff till Adobe körs `clearVars()` funktionen. Implementeringen kan sedan definiera variabler igen utan att oroa dig för felaktigt bestående värden.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
