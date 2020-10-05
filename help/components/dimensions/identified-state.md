---
title: Identifierat läge
description: En flagga som avgör igenkänning av enhetsdiagrammet.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# Identifierat läge

Dimensionen Identifierat tillstånd är specifik för [virtuella rapportsviter för analys](../cda/overview.md) över flera enheter. Den rapporterar om Experience Cloud-ID:t känns igen av enhetsdiagrammet när rapporten körs. Denna dimension är till hjälp när det gäller att förstå hur väl CDA sammanfogar eller&quot;komprimerar&quot; data.

## Fyll den här dimensionen med data

Så länge du har [Cross-device Analytics](../cda/overview.md) konfigurerat för en virtuell rapportserie fungerar den här dimensionen som den ska.

## Dimensioner

Dimensionen innehåller `"Identified"` och `"Unidentified"`.

* **`"Identified"`**: Enhetsdiagrammet känner igen det Experience Cloud-ID som är kopplat till träffen.
* **`"Unidentified"`**: Enhetsdiagrammet känner inte igen Experience Cloud-ID:t eller träffen har inget Experience Cloud-ID.
