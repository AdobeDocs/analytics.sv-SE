---
title: Veckodag/vecka
description: Fastställer om träffen inträffade under en veckodag eller en helg.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Veckodag/vecka

Veckodag/helg [dimension](overview.md) ger information om huruvida träffen inträffade under en veckodag (måndag-fredag) eller en helg (lördag-söndag). Tid för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"Weekday"` och `"Weekend"`. Dimensionsartikeln `"Weekday"` gäller för alla träffar måndag till fredag, medan dimensionsartikeln `"Weekend"` gäller för alla träffar på lördag och söndag.
