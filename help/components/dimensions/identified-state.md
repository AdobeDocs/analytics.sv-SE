---
title: Identifierat läge
description: En flagga som avgör igenkänning av enhetsdiagrammet.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# Identifierat läge

Identifierat tillstånd [dimension](overview.md) är specifikt för [Enhetsövergripande analys](../cda/overview.md) virtuella rapportsviter. Den rapporterar om träffar identifieras (sammanfogas) eller inte av systemet när rapporten körs. Denna dimension är till hjälp när det gäller att förstå hur väl CDA sammanfogar eller&quot;komprimerar&quot; data.

## Fyll den här dimensionen med data

Så länge du har [Enhetsövergripande analys](../cda/overview.md) som är konfigurerad för en virtuell rapportsvit fungerar den här dimensionen som den ska.

## Dimensioner

Dimensionerna innehåller `"Identified"` och `"Unidentified"`.

* **`"Identified"`**: Träffen mappas till en person.
* **`"Unidentified"`**: Träffen är inte mappad till en person och kan inte mappas med någon attribueringsmetod.
