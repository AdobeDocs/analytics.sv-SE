---
title: Identifierat läge
description: En flagga som avgör igenkänning av enhetsdiagrammet.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# Identifierat läge

Dimensionen Identifierat tillstånd är specifik för de virtuella rapporteringssviterna [Cross-Device Analytics](../cda/overview.md). Den rapporterar om Experience Cloud-ID:t känns igen av enhetsdiagrammet när rapporten körs. Denna dimension är till hjälp när det gäller att förstå hur väl CDA sammanfogar eller&quot;komprimerar&quot; data.

## Fyll den här dimensionen med data

Så länge du har [Cross-Device Analytics](../cda/overview.md) konfigurerat för en virtuell rapportsvit fungerar den här dimensionen direkt.

## Dimensioner

Bland Dimensionerna finns `"Identified"` och `"Unidentified"`.

* **`"Identified"`**: Enhetsdiagrammet känner igen det Experience Cloud-ID som är kopplat till träffen.
* **`"Unidentified"`**: Enhetsdiagrammet känner inte igen Experience Cloud-ID:t eller träffen har inget Experience Cloud-ID.
