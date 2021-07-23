---
title: dynamicAccountMatch
description: Variabeln dynamicAccountMatch bestämmer vilket värde som ska användas i dynamiska konton.
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 2%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller -taggar i Adobe Experience Platform.

Variabeln `dynamicAccountMatch` är det värde som `dynamicAccountList` tittar på och jämför dess värden. Om `dynamicAccountSelection` inte är inställt på `true` ignoreras variabeln.

Om variabeln inte definieras är standardvärdet `window.location.host`.

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

* Sidor som sparas på en hårddisk har inte flera definierade `location`-variabler (till exempel är `location.host` tomt). Se till att `s_account` innehåller en standardrapportserie.
* När en sida översätts via en webbaserad översättningsmotor, som Google, fungerar inte det dynamiska kontovalet som avsett. Fyll i den variabla serversidan för `s_account` om du vill ha mer exakt spårning.
