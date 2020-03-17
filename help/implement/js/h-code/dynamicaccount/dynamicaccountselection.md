---
title: dynamicAccountSelection
description: Variabeln dynamicAccountSelection aktiverar eller inaktiverar dynamiskt kontoval.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller Adobe Experience Platform Launch.

Variabeln `dynamicAccountSelection` är en boolesk variabel som avgör om dynamiskt kontoval används.

JavaScript-filen tittar `true`på `dynamicAccountMatch` och om den är inställd på `dynamicAccountList`.

Om den är inställd på `false`, eller om variabeln inte är definierad, ignoreras `dynamicAccountMatch` - och `dynamicAccountList` -variablerna.

Om variabeln inte är definierad är standardvärdet `false`.

## Syntax

```js
s.dynamicAccountSelection = [boolean];
```

## Exempel

```js
s.dynamicAccountSelection = true;
```
