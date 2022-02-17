---
title: Implementera med AJAX
description: Lär dig implementera Adobe Analytics på en webbplats med AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Implementera med AJAX

AJAX är ett sätt att använda JavaScript och HTML för att rensa och generera innehåll utan att läsa in en ny sida.

Adobe Analytics förlitar sig normalt på att sidor laddas om för att återställa Analytics-spårningsobjektet. Varje gång du navigerar till en annan URL återställs alla Analytics-variabler och kan definieras igen. När du använder AJAX på webbplatsen ska du justera implementeringen runt bristen på siduppdateringar för att säkerställa att data inte bevaras inkorrekt mellan träffar.

När du har vidtagit åtgärder för att rensa variabelvärden är implementering av Adobe Analytics på webbplatser som använder AJAX i huvudsak samma som andra implementeringsmetoder.

## Bestämma interaktioner och träfftyper

Eftersom sidor som använder AJAX vanligtvis inte läses in på nytt finns det flera interaktioner som en användare kan utföra på din plats. När du implementerar Adobe Analytics ska du se till att skilja sidvisningar från länkspårningsanrop. Tänk på följande fråga för varje interaktion som en användare kan utföra på din plats:

*När en användare interagerar med min webbplats, ändras den interaktionen tillräckligt mycket av innehållet på sidan för att kvalificera sig som en ny sida?*

* Om svaret är **ja** kan du använda ett spårningsanrop för sidvy (`s.t()`).
* Om svaret är **no** bör du överväga att spåra interaktionen med hjälp av ett länkspårningsanrop (`s.tl()`).

>[!NOTE]
>
>Alla interaktioner eller klick behöver inte spelas in. Tänk noga igenom vilka åtgärder som är viktigast att spåra och skicka data till Adobe i enlighet med detta.

## Rensa variabler på varje sida

Variabelvärden finns kvar på sidor som använder AJAX eftersom sidan inte läses in igen. Det krävs därför en särskild inkvartering för att rensa variabla värden så att de inte kvarstår felaktigt i träffar. Adobe erbjuder [`clearVars`](../vars/functions/clearvars.md) för att enkelt ta bort variabelvärden. Kontrollera att du använder den här funktionen när du har skickat varje träff till Adobe och innan du anger variabelvärden för nästa träff.

>[!TIP]
>
>The `clearVars()` funktionen är inte tillgänglig i H-koden. Om du inte har uppgraderat till AppMeasurement anger du en tom sträng för varje Analytics-variabelvärde.

## Exempel

I följande exempel används enkel JavaScript för att rensa befintliga variabelvärden, ange nya värden och sedan skicka en bildbegäran till Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

I följande exempel visas ett spårningsanrop i `done` återanrop till JQuery `.ajax` funktion:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
