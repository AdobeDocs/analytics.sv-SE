---
description: Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.
title: Mätvärden
uuid: ae2021eb-8b26-4a98-b7a0-ce36bca46753
feature: Rapporter och analyser - Grunderna och analyser
role: Business Practitioner, Administrator
exl-id: ea7a59f3-5a5e-48b2-ae0c-ebc5ec34cd63
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Mätvärden

Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.

## Översikt över mätvärden

Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.

Mätvärden och associerade data visas i rapportkolumnerna. Trafikstatistik visar data om besökarnas volym. Konverteringsstatistik visar data om framgångsrika händelser, som inköp, nedladdningar eller andra åtgärder som du vill att användarna ska vidta på webbplatsen.

[Beräknade ](/help/components/c-calcmetrics/cm-overview.md) mätvärden skapas genom en kombination av mätvärden.

En fullständig lista över mätvärden finns i [Metrisk översikt](/help/components/metrics/overview.md) i användarhandboken för komponenter.

## Välj standardrapportmått

Steg som beskriver hur du väljer standardmått på rapportnivå.

<!-- 

t_metrics_set_default.xml

 -->

1. Kör en rapport.
1. Lägg till de mått som du vill spara som standardmått.
1. Klicka på listrutan **[!UICONTROL Add Metrics]** och välj **[!UICONTROL Set as Default]**.

   De valda måtten sparas som standardvärden för den här rapporten. Följande information gäller standardvärden:

* Standardvärden gäller för alla användarkonton, men är per rapport och rapportserie. Alla användare som till exempel visar en viss rapport i samma rapportserie visar de mätvärden som angetts med föregående procedur.
* Om du växlar mellan rapporter behålls de mätvärden som visades i den senast visade rapporten. Om du vill visa standardmått i den nya rapporten klickar du på listrutan [!UICONTROL Add Metrics] och sedan på [!UICONTROL Show Defaults].

* Om du klickar på [!UICONTROL Clear Defaults] tas standardmåtten för den rapporten bort och återställs till de ursprungliga standardmåtten för rapporten ( [!UICONTROL Page Views] för utkast och det du har angett i Administratörsverktyg för eVars).
