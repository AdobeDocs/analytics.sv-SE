---
title: Innehållshastighet
description: Innehållshastigheten mäter effekten av innehåll i efterföljande led.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
source-git-commit: 26e166e065df90cb327fe1106542e17831069141
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---

# Innehållshastighet

Med det beräknade innehållshastigheten kan du mäta hur en dimension (vanligtvis [[!UICONTROL Page]](/help/components/dimensions/page.md)) bidrar till att användarna spenderar tid på er webbplats eller i er app.

Det här måttet använder [Deltagande](/help/analyze/analysis-workspace/attribution/models.md) på [Sidvyer](page-views.md) som en del av beräkningen. När man träffar en sida vid besöket får alla sidor som tidigare träffats under samma besök också poäng för sidvisningen. Den här formeln innebär vanligtvis att ju tidigare en sida trycks ned under ett besök, desto mer kredit får den. (Se [Sidvyer (deltagande | Besök) eller Besök deltagandet](#page-views-participation--visit-or-visit-participation) för mer information.)

## Beräkning

&#39;Innehållshastighet&#39; är en standardberäkning [mått](overview.md) och använder formeln `Page views (Visit participation)` dividerat med `Visits`.

![](assets/cont-velo-1.png)

## Vanliga användningsområden

[!UICONTROL Content Velocity] används ofta i innehållsanalys tillsammans med andra viktiga mätvärden som [!UICONTROL Page Views], [!UICONTROL Visits]och [!UICONTROL Bounce Rate].

![](assets/cont-velo-3.png)

## Exempel

I följande exempel bryts de två delarna av innehållets hastighet: &quot;Sidvyer (deltagande) | Besök) och Besök.

### Sidvyer (deltagande | Besök) eller Besök deltagandet

Tänk på följande exempel på hur besöksdeltagandet påverkar attribuering:

På en webbplats besöker en användare följande sidor i den här ordningen:

* Sida A
* Sida B
* Sida C
* Sida D

I exemplet ovan skulle Page A få en belöning för 4 träffar, Page B för 3 träffar, Page C för 2 träffar och Page D för 1 träffar.

I följande exempel visas samma princip, men vissa sidor besöktes mer än en gång.

* Sida A
* Sida B
* Sida C
* Sida B
* Sida D
* Sida A

I exemplet ovan får sida A krediter för 7 träffar, sida B för 8 träffar, sida C för 4 träffar och sida D för 2 träffar.

### Besök

Efter det att besökets deltagande har beräknats delas resultatet av antalet besök.
