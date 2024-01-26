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
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i de aktuella AppMeasurementen bibliotek eller taggar i Adobe Experience Platform.

The `dynamicAccountMatch` variabeln är värdet som `dynamicAccountList` tittar på och jämför dess värden. If `dynamicAccountSelection` är inte inställd på `true`ignoreras variabeln.

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

* Sidor som sparats på en hårddisk har inte flera `location` variabler definierade (till exempel `location.host` är tomt). Kontrollera att `s_account` innehåller en standardrapportsserie.
* När en sida översätts via en webbaserad översättningsmotor, som Google, fungerar inte det dynamiska kontovalet som avsett. För mer exakt spårning fyller du i `s_account` variabel på serversidan.
