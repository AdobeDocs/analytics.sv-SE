---
title: dynamicAccountMatch
description: Variabeln dynamicAccountMatch bestämmer vilket värde som ska användas i dynamiska konton.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 2%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller -taggar i Adobe Experience Platform.

The `dynamicAccountMatch` variabeln är värdet som `dynamicAccountList` tittar på och jämför dess värden. If `dynamicAccountSelection` är inte inställd på `true`, ignoreras den här variabeln.

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

* Sidor som sparats på en hårddisk har inte flera `location` variabler definierade (till exempel `location.host` är tomt). Se till att `s_account` innehåller en standardrapportsserie.
* När en sida översätts via en webbaserad översättningsmotor, som Google, fungerar inte det dynamiska kontovalet som avsett. Om du vill ha mer exakt spårning fyller du i `s_account` variabel på serversidan.
