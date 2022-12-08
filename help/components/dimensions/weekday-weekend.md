---
title: Veckodag/Veckoslut
description: Fastställer om träffen inträffade under en veckodag eller en helg.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Veckodag/Veckoslut

Dimensionen &#39;Veckodag/helg&#39; ger insikter om huruvida träffen inträffade under en veckodag (måndag-fredag) eller en helg (lördag-söndag). Tid för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"Weekday"` och `"Weekend"`. Dimensionsartikeln `"Weekday"` gäller för alla träffar måndag till fredag, medan dimensionsartikeln `"Weekend"` gäller för alla träffar på lördag och söndag.
