---
title: registerPostTrackCallback
description: Skapa callback-funktioner när du har skickat en träff till Adobe.
feature: Appmeasurement Implementation
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# registerPostTrackCallback

Variabeln `registerPostTrackCallback` gör att din organisation kan koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in av AppMeasurement till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!WARNING]
>
>Gör inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti variabeln `registerPostTrackCallback`. Om du anger spårningsanrop i den här variabeln skapas en oändlig slinga med bildbegäranden!

Varje gång du anropar variabeln `registerPostTrackCallback` kopplar du den funktionen till körning omedelbart efter att en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidsangivelsen och ordningen för funktioner som utlösts mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` garanteras inte. Undvik beroenden mellan dessa två funktioner.

## Återanrop efter spår med tillägget Web SDK

Kommer snart!

## Efterspårsåteranrop som manuellt implementerar Web SDK

Du kan använda en JavaScript Promise när du skickar en händelse för att registrera en funktion efter att data har skickats till Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Mer information finns i [Hantera svar från händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=sv-SE#handling-responses-from-events) i Web SDK-dokumentationen.

## Registrera återanrop efter spår med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.registerPostTrackCallback i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

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
