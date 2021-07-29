---
title: registerPostTrackCallback
description: Skapa callback-funktioner när du har skickat en träff till Adobe.
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# registerPostTrackCallback

Variabeln `registerPostTrackCallback` gör att din organisation kan koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!IMPORTANT]
>
>Anropa inga spårningsanrop som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti variabeln `registerPostTrackCallback`. Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du anropar variabeln `registerPostTrackCallback` kopplar du den funktionen till körning omedelbart efter att en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidsangivelsen och ordningen för funktioner som utlösts mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` är inte garanterad. Undvik beroenden mellan dessa två funktioner.

## Registrera återanrop efter spår med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPostTrackCallback i AppMeasurement och anpassad kodredigerare

`s.registerPostTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs omedelbart när en bildbegäran har skickats.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden refererar du till strängargumentet `requestUrl` i den kapslade funktionen. Du kan analysera variabeln `requestUrl` för att kunna använda den. om du justerar den här variabeln påverkas inte datainsamlingen.

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

## Exempel på användningsfall

Det kan vara bra att registrera funktionen [`clearVars()`](clearvars.md) i återanropet efter spåret för enkelsidiga program. Varje gång du skickar en träff till Adobe körs funktionen `clearVars()`. Implementeringen kan sedan definiera variabler igen utan att oroa dig för felaktigt bestående värden.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
