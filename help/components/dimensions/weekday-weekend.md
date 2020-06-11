---
title: Veckodag/Veckoslut
description: Fastställer om träffen inträffade under en veckodag eller en helg.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---


# Veckodag/Veckoslut

Dimensionen &#39;Veckodag/helg&#39; ger insikter om huruvida träffen inträffade under en veckodag (måndag-fredag) eller en helg (lördag-söndag). Tidpunkten för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsvärden

Den här dimensionen innehåller alltid exakt två dimensionsvärden: `"Weekday"` och `"Weekend"`. Dimensionsvärdet `"Weekday"` gäller alla träffar måndag till fredag, medan dimensionsvärdet `"Weekend"` gäller alla träffar på lördag och söndag.
