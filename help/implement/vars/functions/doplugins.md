---
title: doPlugins
description: Konfigurera logik precis innan en träff kompileras och skickas till Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# doPlugins

The `doPlugins` variabeln fungerar som ett&quot;sista anrop&quot; för att ange värden i implementeringen. If [`usePlugins`](../config-vars/useplugins.md) är aktiverat körs den automatiskt precis innan någon typ av bildbegäran kompileras och skickas till Adobe, inklusive:

* All sidvy ([`t()`](t-method.md)) samtal
* All länkspårning ([`tl()`](tl-method.md)), inklusive automatiska nedladdningslänkar och avslutningslänkar

Använd `doPlugins` variabel för att anropa plugin-kod och ange slutliga variabelvärden precis innan en bildbegäran kompileras och skickas till Adobe.

## Plugin-program som använder taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.doPlugins in AppMeasurement and custom code

Ange `s.doPlugins` till en funktion som innehåller önskad kod. Funktionen körs automatiskt när du gör ett spårningsanrop.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Ange en funktion för `doPlugins` endast en gång i implementeringen. Om du anger `doPlugins` variabel mer än en gång, används bara den senaste koden.

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
>Tidigare versioner av AppMeasurement hade något annorlunda `doPlugins()` kod. Adobe rekommenderar att du använder formatet ovan som en god praxis.
