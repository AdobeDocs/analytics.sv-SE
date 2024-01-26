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

The `registerPostTrackCallback` kan din organisation koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in av AppMeasurementet till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!WARNING]
>
>Gör inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) innanför `registerPostTrackCallback` variabel. Om du anger spårningsanrop i den här variabeln skapas en oändlig slinga med bildbegäranden!

Varje gång du ringer `registerPostTrackCallback` kan du koppla funktionen till den så att den körs direkt när en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidpunkt och ordning för de funktioner som utlöses mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` är inte garanterade. Undvik beroenden mellan dessa två funktioner.

## Återanrop efter spår med tillägget Web SDK

Kommer snart!

## Efterspårets återanrop implementerar Web SDK manuellt

Du kan använda ett JavaScript-uttryck när du skickar en händelse för att registrera en funktion efter att data har skickats till Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Se [Hantera svar från händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) finns i Web SDK-dokumentationen.

## Registrera återanrop efter spår med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.registerPostTrackCallback i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.registerPostTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs omedelbart när en bildbegäran har skickats.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden ska du referera till `requestUrl` strängargument i den kapslade funktionen. Du kan analysera `requestUrl` -variabel för det du vill använda. Om du justerar den här variabeln påverkas inte datainsamlingen.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ytterligare argument kan inkluderas i `s.registerPostTrackCallback` som kan användas i den kapslade funktionen:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Använd skiftläge

Registrerar [`clearVars()`](clearvars.md) funktionen i återanropet efter spåret kan vara bra för enkelsidiga program. Varje gång du skickar en träff till Adobe `clearVars()` funktionen körs. Implementeringen kan sedan definiera variabler igen utan att oroa dig för felaktigt bestående värden.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
