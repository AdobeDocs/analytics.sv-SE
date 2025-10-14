---
title: Veckodag/vecka
description: Fastställer om träffen inträffade under en veckodag eller en helg.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Veckodag/vecka

Dimensionen [&#x200B; för veckodag/helg &#x200B;](overview.md)ger information om huruvida träffen inträffade under en veckodag (måndag-fredag) eller helg (lördag-söndag). Tid för träffen baseras på [rapportsvitens tidszon](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimension-objekt

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"Weekday"` och `"Weekend"`. Dimensionsobjektet `"Weekday"` gäller för alla träffar måndag till fredag, medan dimensionsobjektet `"Weekend"` gäller för alla träffar på lördag och söndag.
