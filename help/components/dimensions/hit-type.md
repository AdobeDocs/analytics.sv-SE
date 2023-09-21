---
title: Träff-typ
description: Avgör om träffen var en förgrunds- eller bakgrundsträff.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Träff-typ

Träff-typen [dimension](overview.md) Fastställer om en mobilapp fanns i förgrunden eller bakgrunden när träffen skickades till datainsamlingsservrarna i Adobe. Den här dimensionen är bara relevant för att rapportera programsviter som innehåller data för mobilprogram. Webbläsardata som samlas in via AppMeasurementet rapporterar alltid träffen som &quot;Förgrund&quot;.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla SDK-implementeringar för mobila enheter i version 4.13.6 eller senare. Om du inte använder mobil-SDK, alla träffar-listor under dimensionsobjektet &quot;Förgrund&quot;. Om Inaktivera äldre rapportering och attribuering för bakgrundstips är markerat visas endast bakgrundsträffar i [Virtuella rapportsviter](../vrs/vrs-mobile-visit-processing.md).

## Dimensioner

Dimensionerna innehåller `"Foreground"` och `"Background"`. En träff som inte skickades i bakgrunden av ett mobilprogram tillhör `"Foreground"` dimensionsobjekt. Alla träffar som skickas där mobilprogrammet fanns i bakgrunden tillhör `"Background"` dimensionsobjekt.
