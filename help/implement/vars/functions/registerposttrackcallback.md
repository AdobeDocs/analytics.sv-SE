---
title: registerPostTrackCallback
description: Skapa callback-funktioner när du har skickat en träff till Adobe.
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# registerPostTrackCallback

Variabeln `registerPostTrackCallback` gör att din organisation kan koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in av AppMeasurementet till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!WARNING]
>
>Gör inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti variabeln `registerPostTrackCallback`. Om du anger spårningsanrop i den här variabeln skapas en oändlig slinga med bildbegäranden!

Varje gång du anropar variabeln `registerPostTrackCallback` kopplar du den funktionen till körning omedelbart efter att en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidsangivelsen och ordningen för funktioner som utlösts mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` garanteras inte. Undvik beroenden mellan dessa två funktioner.

## Post-track-återanrop med Web SDK-tillägget

Kommer snart!

## Post-track-återanrop som implementerar Web SDK manuellt

Du kan använda en JavaScript Promise när du skickar en händelse för att registrera en funktion efter att data har skickats till Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Mer information finns i [Hantera svar från händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#handling-responses-from-events) i Web SDK-dokumentationen.

## Registrera Post-track-återanrop med tillägget Adobe Analytics

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.registerPostTrackCallback i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

`s.registerPostTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs omedelbart när en bildbegäran har skickats.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet `requestUrl` i den kapslade funktionen. Du kan tolka variabeln `requestUrl` om du vill använda den. Om du justerar variabeln påverkas inte datainsamlingen.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ytterligare argument kan inkluderas i funktionen `s.registerPostTrackCallback`, som kan användas i den kapslade funktionen:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Använd skiftläge

Det kan vara bra att registrera funktionen [`clearVars()`](clearvars.md) i återanropet efter spåret för enkelsidiga program. Varje gång du skickar en träff till Adobe körs funktionen `clearVars()`. Implementeringen kan sedan definiera variabler igen utan att oroa dig för felaktigt bestående värden.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
