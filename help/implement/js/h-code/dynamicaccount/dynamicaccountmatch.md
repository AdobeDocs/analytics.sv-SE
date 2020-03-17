---
title: dynamicAccountMatch
description: Variabeln dynamicAccountMatch bestämmer vilket värde som ska användas i dynamiska konton.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller Adobe Experience Platform Launch.

Variabeln `dynamicAccountMatch` är det värde som `dynamicAccountList` tittar på och jämför dess värden. Om `dynamicAccountSelection` inte anges till `true`ignoreras variabeln.

Om variabeln inte är definierad är standardvärdet `window.location.host`.

## Syntax

```js
s.dynamicAccountMatch=[DOM object]
```

## Exempel

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Ytterligare information

* Sidor som sparas på en hårddisk har inte flera definierade `location` variabler (t.ex. `location.host` är tomma). Kontrollera att `s_account` innehåller en standardrapportsserie.
* När en sida översätts via en webbaserad översättningsmotor, som Google, fungerar inte det dynamiska kontovalet som avsett. Fyll i den variabla serversidan för mer exakt spårning `s_account` .
