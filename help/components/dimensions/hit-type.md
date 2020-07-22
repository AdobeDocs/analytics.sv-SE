---
title: Träff-typ
description: Avgör om träffen var en förgrunds- eller bakgrundsträff.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Träff-typ

Dimensionen Träffyp avgör om en mobilapp fanns i förgrunden eller bakgrunden när träffen skickades till Adobes datainsamlingsservrar. Den här dimensionen är bara relevant för att rapportera programsviter som innehåller data för mobilprogram. Webbläsardata som samlats in via AppMeasurement rapporterar alltid träffen som &quot;Förgrund&quot;.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla SDK-implementeringar för mobila enheter i version 4.13.6 eller senare. Om du inte använder mobil-SDK, alla träffar-listor under dimensionsobjektet &quot;Förgrund&quot;. Om Inaktivera äldre rapportering och attribuering för bakgrundstötlar är markerat visas endast bakgrundstötningar i [virtuella rapportsviter](../vrs/vrs-mobile-visit-processing.md).

## Dimensionsobjekt

Dimensionsobjekten omfattar `"Foreground"` och `"Background"`. Alla träffar som inte skickades i bakgrunden i ett mobilprogram tillhör `"Foreground"` dimensionsobjektet. Alla träffar som skickas där mobilprogrammet fanns i bakgrunden tillhör `"Background"` dimensionsobjektet.
