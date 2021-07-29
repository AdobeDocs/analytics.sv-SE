---
title: doPlugins
description: Konfigurera logik precis innan en träff kompileras och skickas till Adobe.
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# doPlugins

Variabeln `doPlugins` fungerar som ett&quot;sista anrop&quot; för att ange värden i implementeringen. Om [`usePlugins`](../config-vars/useplugins.md) är aktiverat körs den automatiskt precis innan någon typ av bildbegäran kompileras och skickas till Adobe, inklusive:

* Alla sidvyanrop ([`t()`](t-method.md))
* Alla länkspårningsanrop ([`tl()`](tl-method.md)), inklusive automatiska hämtningslänkar och avslutslänkar

Använd variabeln `doPlugins` för att anropa plugin-kod och ange slutgiltiga variabelvärden precis innan en bildbegäran kompileras och skickas till Adobe.

## Plugin-program som använder taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.doPlugins in AppMeasurement and custom code

Ange variabeln `s.doPlugins` till en funktion som innehåller önskad kod. Funktionen körs automatiskt när du gör ett spårningsanrop.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Ange en funktion för variabeln `doPlugins` endast en gång i implementeringen. Om du anger variabeln `doPlugins` mer än en gång används bara den senaste koden.

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

>[!NOTE]
>
>Tidigare versioner av AppMeasurement hade något annorlunda `doPlugins()`-kod. Adobe rekommenderar att du använder formatet ovan som en god praxis.
