---
title: Träff-typ
description: Avgör om träffen var en förgrunds- eller bakgrundsträff.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Träff-typ

Träfftypen [dimension](overview.md) avgör om en mobilapp fanns i förgrunden eller bakgrunden när träffen skickades till datainsamlingsservrar i Adobe. Den här dimensionen är bara relevant för att rapportera programsviter som innehåller data för mobilprogram. Webbläsardata som samlas in via AppMeasurementet rapporterar alltid träffen som &quot;Förgrund&quot;.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla SDK-implementeringar för mobila enheter i version 4.13.6 eller senare. Om du inte använder mobil-SDK, alla träffar-listor under dimensionsobjektet &quot;Förgrund&quot;. Om Inaktivera äldre rapportering och attribuering för bakgrundstips är markerat visas endast bakgrundsträffar i [virtuella rapportsviter](../vrs/vrs-mobile-visit-processing.md).

## Dimensioner

Dimensionen innehåller `"Foreground"` och `"Background"`. Alla träffar som inte skickades i bakgrunden för ett mobilprogram tillhör dimensionsobjektet `"Foreground"`. Alla träffar som skickas där mobilprogrammet fanns i bakgrunden tillhör dimensionsobjektet `"Background"`.
