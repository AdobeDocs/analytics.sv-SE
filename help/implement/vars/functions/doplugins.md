---
title: doPlugins
description: Konfigurera logik precis innan en träff kompileras och skickas till Adobe.
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# doPlugins

Variabeln fungerar som ett&quot;sista anrop&quot; för att ange värden i implementeringen. `doPlugins` Om `usePlugins` så är `true`fallet körs den automatiskt precis innan någon typ av bildförfrågan kompileras och skickas till Adobe, inklusive:

* Alla sidvysamtal (`t`på eng)
* Alla länkspårningsanrop (`tl`inklusive automatiska hämtningslänkar och avslutningslänkar)

Använd variabeln för att anropa plugin-programkod och ange slutliga variabelvärden precis innan en bildbegäran kompileras och skickas till Adobe. `doPlugins`

## Plugin-program i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.doPlugins in AppMeasurement and Launch custom code

Ställ in variabeln på en funktion som innehåller önskad kod. `s.doPlugins` Funktionen körs automatiskt när du gör ett spårningsanrop.

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] Ställ bara in en funktion på `doPlugins` variabeln en gång i implementeringen. Om du anger variabeln mer än en gång används bara den senaste koden. `doPlugins`

## Exempel

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

> [!NOTE] Tidigare versioner av AppMeasurement hade något annorlunda `doPlugins()` kod. Adobe rekommenderar att du använder ovanstående format som en god praxis.
