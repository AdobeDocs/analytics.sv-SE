---
title: Träff-typ
description: Avgör om träffen var en förgrunds- eller bakgrundsträff.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Träff-typ

Dimensionen Träffyp avgör om en mobilapp fanns i förgrunden eller bakgrunden när träffen skickades till Adobe datainsamlingsservrar. Den här dimensionen är bara relevant för att rapportera programsviter som innehåller data för mobilprogram. Webbläsardata som samlats in via AppMeasurement rapporterar alltid träffen som &quot;Förgrund&quot;.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla SDK-implementeringar för mobila enheter i version 4.13.6 eller senare. Om du inte använder mobil-SDK, alla träffar-listor under dimensionsobjektet &quot;Förgrund&quot;. Om Inaktivera äldre rapportering och attribuering för bakgrundstips är markerat visas endast bakgrundsträffar i [Virtuella rapportsviter](../vrs/vrs-mobile-visit-processing.md).

## Dimensioner

Dimensionerna innehåller `"Foreground"` och `"Background"`. En träff som inte skickades i bakgrunden av ett mobilprogram tillhör `"Foreground"` dimensionsobjekt. Alla träffar som skickas där mobilprogrammet fanns i bakgrunden tillhör `"Background"` dimensionsobjekt.
