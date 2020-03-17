---
description: Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.
title: Mått
topic: Reports and analytics
uuid: ae2021eb-8b26-4a98-b7a0-ce36bca46753
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mått

Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.

## Mått

Mätvärden är grunden för rapporter och hjälper er att visa och förstå dataförhållanden och möjliggör jämförelser sida vid sida av olika datauppsättningar om er webbplats. Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare.

Mätvärden och associerade data visas i rapportkolumnerna. Trafikstatistik visar data om besökarnas volym. Konverteringsstatistik visar data om framgångsrika händelser, som inköp, nedladdningar eller andra åtgärder som du vill att användarna ska vidta på webbplatsen.

[Beräknade mätvärden](/help/components/c-calcmetrics/cm-overview.md) skapas genom en kombination av mätvärden.

Mer information om definitioner finns i Översikt över [mått](/help/components/c-variables/c-metrics/metricslist.md)

## Välj standardrapportmått

Steg som beskriver hur du väljer standardmått på rapportnivå.

<!-- 

t_metrics_set_default.xml

 -->

1. Kör en rapport.
1. Lägg till de mått som du vill spara som standardmått.
1. Klicka på den **[!UICONTROL Add Metrics]** nedrullningsbara listan och välj sedan **[!UICONTROL Set as Default]**.

   De valda måtten sparas som standardvärden för den här rapporten. Följande information gäller standardvärden:

* Standardvärden gäller för alla användarkonton, men är per rapport och rapportserie. Alla användare som till exempel visar en viss rapport i samma rapportserie visar de mätvärden som angetts med föregående procedur.
* Om du växlar mellan rapporter behålls de mätvärden som visades i den senast visade rapporten. Om du vill visa standardvärden i den nya rapporten klickar du på [!UICONTROL Add Metrics] listrutan och sedan på [!UICONTROL Show Defaults].

* När du klickar [!UICONTROL Clear Defaults] tas standardmåtten för den rapporten bort och de återställs till de ursprungliga standardmåtten för rapporten ( [!UICONTROL Page Views] för props, och det du har angett i Administratörsverktyg för eVars).

