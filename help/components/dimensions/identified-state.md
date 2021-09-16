---
title: Identifierat läge
description: En flagga som avgör igenkänning av enhetsdiagrammet.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 1a58c3e87f5918c91b891faa6027f5ad8b6024b9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---

# Identifierat läge

Dimensionen Identifierat tillstånd är specifik för de virtuella rapporteringssviterna [Cross-Device Analytics](../cda/overview.md). Den rapporterar om träffar identifieras (sammanfogas) eller inte av systemet när rapporten körs. Denna dimension är till hjälp när det gäller att förstå hur väl CDA sammanfogar eller&quot;komprimerar&quot; data.

## Fyll den här dimensionen med data

Så länge du har [Cross-Device Analytics](../cda/overview.md) konfigurerat för en virtuell rapportsvit fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns `"Identified"` och `"Unidentified"`.

* **`"Identified"`**: Träffen mappas till en person.
* **`"Unidentified"`**: Träffen är inte mappad till en person och kan inte mappas med någon attribueringsmetod.
