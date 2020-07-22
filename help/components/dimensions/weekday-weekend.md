---
title: Veckodag/Veckoslut
description: Fastställer om träffen inträffade under en veckodag eller en helg.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---


# Veckodag/Veckoslut

Dimensionen &#39;Veckodag/helg&#39; ger insikter om huruvida träffen inträffade under en veckodag (måndag-fredag) eller en helg (lördag-söndag). Tidpunkten för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"Weekday"` och `"Weekend"`. Dimensionsobjektet `"Weekday"` gäller alla träffar måndag till fredag, medan dimensionsobjektet `"Weekend"` gäller alla träffar på lördag och söndag.
