---
title: registerPostTrackCallback
description: Skapa callback-funktioner när du har skickat en träff till Adobe.
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# registerPostTrackCallback

The `registerPostTrackCallback` kan din organisation koppla en JavaScript-funktion omedelbart efter att en träff har skickats till Adobe. Om ett spårningsanrop misslyckas körs inte den här funktionen. Du kan använda den här variabeln för att skicka data som samlats in med AppMeasurement till en partner eller intern infrastruktur, eller för att rensa upp variabelvärden i enkelsidiga program.

>[!IMPORTANT]
>
>Anropa inga spårningssamtal som [`t()`](t-method.md) eller [`tl()`](tl-method.md) inuti `registerPostTrackCallback` variabel. Spårningsfunktionerna i den här variabeln orsakar en oändlig slinga med bildbegäranden!

Varje gång du ringer `registerPostTrackCallback` kan du koppla funktionen till den så att den körs direkt när en bildbegäran har skickats. Undvik att registrera samma funktion flera gånger i samma sidinläsning.

>[!NOTE]
>
>Tidpunkt och ordning för de funktioner som utlöses mellan [`registerPreTrackCallback`](registerpretrackcallback.md) och `registerPostTrackCallback` är inte garanterade. Undvik beroenden mellan dessa två funktioner.

## Registrera återanrop efter spår med hjälp av taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.registerPostTrackCallback i AppMeasurement och anpassad kodredigerare

The `s.registerPostTrackCallback` är en funktion som tar en funktion som enda argument. Den kapslade funktionen körs omedelbart när en bildbegäran har skickats.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Om du vill använda URL:en för bildbegäran i koden ska du referera till `requestUrl` strängargument i den kapslade funktionen. Du kan analysera `requestUrl` variabel för det du vill använda, om du justerar den här variabeln påverkas inte datainsamlingen.

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

## Exempel på användningsfall

Registrerar [`clearVars()`](clearvars.md) funktionen i återanropet efter spåret kan vara bra för enkelsidiga program. Varje gång du skickar en träff till Adobe `clearVars()` funktionen körs. Implementeringen kan sedan definiera variabler igen utan att oroa dig för felaktigt bestående värden.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
