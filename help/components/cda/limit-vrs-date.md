---
title: Begränsa ett virtuellt rapportpaket till vissa datum
description: Lär dig hur du begränsar ett datumintervall för en virtuell rapportserie så att det bara fokuserar på sammanslagna data.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Begränsa ett virtuellt rapportpaket till vissa datum

{{available-existing-customers}}

När vi aktiverar stygn börjar stygn på ett visst datum. Låt oss anta att datumet är 1 juni. Den virtuella CDA-rapportsviten kommer att innehålla icke sammansatta data före den 1 juni. Du kanske vill dölja alla data i den virtuella rapportsviten före 1 juni så att analysen kan fokusera på datumintervall efter att sammanfogningen påbörjats.

Du kan begränsa den virtuella rapportsvitens data till vissa datum genom att göra följande:

## Steg 1: Skapa en virtuell rapportsvit med ett rullande datumintervall

När du konfigurerar den virtuella rapportsviten, under Komponenter, lägger du till i ett datumintervall som har en fast start med ett rullande datumintervall. Den fasta början bör vara dagen då sammanfogningen började.

![](assets/rolling-daily.png)

## Steg 2: Skapa ett exkluderingssegment

Skapa sedan ett träffsegment som placerar datumintervallet i en exkluderingsbehållare inuti en annan exkluderingsbehållare. Det är en exkludering.

Orsaken till&quot;exclude exclude&quot; är att datumintervall är avsedda att åsidosätta rapportens datumintervall. Om du bara skickar in den 1 juni kommer rapportens datumintervall alltid att bli den 1 juni framåt. Detta kommer att leda till oönskade resultat. När du&quot;exkluderar&quot; åsidosätter den det här beteendet och begränsar bara de data du kan rita från till rätt datumintervall.

![](assets/exclude-exclude.png)

## Steg 3: Använd det här segmentet i den virtuella rapportsviten för analyser över olika enheter

![](assets/apply-segment.png)

## Steg 4: Se resultaten i rapporteringen

Observera att rapporteringen nu börjar på det önskade datumet, samma dag som sammanslagningen först implementerades:

![](assets/report-limited-dates.png)
