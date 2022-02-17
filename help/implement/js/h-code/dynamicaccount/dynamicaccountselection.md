---
title: dynamicAccountSelection
description: Variabeln dynamicAccountSelection aktiverar eller inaktiverar dynamiskt kontoval.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 2%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller i användargränssnittet för datainsamling.

The `dynamicAccountSelection` är en boolesk variabel som avgör om dynamiskt kontoval används.

Om inställt på `true`, tittar JavaScript-filen på `dynamicAccountMatch` och `dynamicAccountList`.

Om inställt på `false`eller om variabeln inte är definierad `dynamicAccountMatch` och `dynamicAccountList` variabler ignoreras.

Om variabeln inte är definierad är standardvärdet `false`.

## Syntax

```js
s.dynamicAccountSelection = [boolean];
```

## Exempel

```js
s.dynamicAccountSelection = true;
```
