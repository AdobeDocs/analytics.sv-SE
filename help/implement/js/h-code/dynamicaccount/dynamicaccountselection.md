---
title: dynamicAccountSelection
description: Variabeln dynamicAccountSelection aktiverar eller inaktiverar dynamiskt kontoval.
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 2%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller i användargränssnittet för datainsamling.

Variabeln `dynamicAccountSelection` är en boolesk variabel som avgör om dynamiskt kontoval används.

Om den anges till `true` söker JavaScript-filen på `dynamicAccountMatch` och `dynamicAccountList`.

Om den är inställd på `false`, eller om variabeln inte är definierad, ignoreras variablerna `dynamicAccountMatch` och `dynamicAccountList`.

Om variabeln inte är definierad är standardvärdet `false`.

## Syntax

```js
s.dynamicAccountSelection = [boolean];
```

## Exempel

```js
s.dynamicAccountSelection = true;
```
