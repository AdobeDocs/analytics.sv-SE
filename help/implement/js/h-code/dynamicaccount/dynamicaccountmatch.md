---
title: dynamicAccountMatch
description: Variabeln dynamicAccountMatch bestämmer vilket värde som ska användas i dynamiska konton.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Dynamiska konton stöds endast med äldre JavaScript-implementeringar (H Code). Dessa variabler stöds inte i de aktuella AppMeasurementen bibliotek eller taggar i Adobe Experience Platform.

Variabeln `dynamicAccountMatch` är det värde som `dynamicAccountList` tittar på och jämför dess värden. Om `dynamicAccountSelection` inte är inställd på `true` ignoreras variabeln.

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

* Sidor som sparas på en hårddisk har inte flera definierade `location`-variabler (till exempel är `location.host` tomt). Kontrollera att `s_account` innehåller en standardrapportsserie.
* När en sida översätts via en webbaserad översättningsmotor, som Google, fungerar inte det dynamiska kontovalet som avsett. Fyll i `s_account`-variabelns serversida om du vill ha mer exakt spårning.
