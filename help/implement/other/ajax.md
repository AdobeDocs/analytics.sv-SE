---
title: Implementera med AJAX
description: Lär dig hur du implementerar Adobe Analytics på en webbplats med AJAX.
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Implementera med AJAX

AJAX är ett sätt att använda JavaScript och HTML för att rensa och generera innehåll utan att läsa in en ny sida.

Adobe Analytics förlitar sig vanligtvis på att sidor läses in igen för att återställa Analytics-spårningsobjektet. Varje gång du navigerar till en annan URL återställs alla Analytics-variabler och kan definieras igen. När du använder AJAX på din webbplats bör du justera implementeringen runt bristen på siduppdateringar för att säkerställa att data inte bevaras inkorrekt mellan träffar.

När ni har åtgärder för att rensa variabelvärden är Adobe Analytics på webbplatser som använder AJAX i huvudsak detsamma som andra implementeringsmetoder.

## Bestämma interaktioner och träfftyper

Eftersom sidor som använder AJAX vanligtvis inte läses in på nytt finns det flera interaktioner som en användare kan utföra på din webbplats. När du implementerar Adobe Analytics ska du se till att skilja sidvisningar från länkspårningsanrop. Tänk på följande fråga för varje interaktion som en användare kan utföra på din plats:

*När en användare interagerar med min webbplats, ändras den interaktionen tillräckligt mycket av innehållet på sidan för att kvalificera sig som en ny sida?*

* Om svaret är **ja** kan du använda ett spårningsanrop (`s.t()`) för sidvyn.
* Om svaret är **nej** bör du spåra interaktionen med ett länkspårningsanrop (`s.tl()`).

> [!NOTE] Alla interaktioner eller klick behöver inte spelas in. Tänk noga igenom vilka åtgärder som är viktigast att spåra och skicka data till Adobe i enlighet med detta.

## Rensa variabler på varje sida

Variabelvärden finns kvar på sidor som använder AJAX eftersom sidan inte läses in igen. Det krävs därför en särskild inkvartering för att rensa variabla värden så att de inte kvarstår felaktigt i träffar. Adobe erbjuder en funktion som [`clearVars`](../vars/functions/clearvars.md) enkelt tar bort variabelvärden. Kontrollera att du använder den här funktionen när du har skickat varje träff till Adobe och innan du anger variabelvärden för nästa träff.

> [!TIP] Funktionen `clearVars()` är inte tillgänglig i H-koden. Om du inte har uppgraderat till AppMeasurement anger du en tom sträng för varje Analytics-variabelvärde.

## Exempel

I följande exempel används enkel JavaScript för att rensa befintliga variabelvärden, ange nya värden och sedan skicka en bildbegäran till Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

I följande exempel visas ett spårningsanrop i återanropet till `done` JQuery- `.ajax` funktionen:

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
