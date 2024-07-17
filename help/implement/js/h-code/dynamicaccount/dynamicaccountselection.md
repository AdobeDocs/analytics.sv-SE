---
title: dynamicAccountSelection
description: Variabeln dynamicAccountSelection aktiverar eller inaktiverar dynamiskt kontoval.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Dynamiska konton stöds endast med äldre JavaScript-implementeringar (H Code). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller Adobe Experience Platform Data Collection.

Variabeln `dynamicAccountSelection` är en boolesk variabel som avgör om dynamiskt kontoval används.

Om värdet är `true` söker JavaScript-filen efter `dynamicAccountMatch` och `dynamicAccountList`.

Om värdet är `false`, eller om variabeln inte är definierad, ignoreras variablerna `dynamicAccountMatch` och `dynamicAccountList`.

Om variabeln inte definieras är standardvärdet `false`.

## Syntax

```js
s.dynamicAccountSelection = [boolean];
```

## Exempel

```js
s.dynamicAccountSelection = true;
```
