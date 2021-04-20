---
description: Steg som beskriver hur du anpassar diagrammet så att det är mest användbart för den avsedda målgruppen.
title: Ändra rapportdiagram
uuid: c2e81c6c-bfe9-4457-8b5d-512255ca9711
feature: Reports & Analytics Basics & Analytics Basics
role: Business Practitioner, Administrator
exl-id: 5a098b38-0939-4dd2-9a05-1b6b678f2d50
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 1%

---

# Ändra rapportdiagram

Steg som beskriver hur du anpassar diagrammet så att det är mest användbart för den avsedda målgruppen.

Vilken typ av diagram som är tillgängliga beror på vilken typ av rapport du kör. Trend Line-diagram är till exempel användbara för trendrapporter, men du kan också använda ett vertikalt liggande diagram med trendlinjer som tydligt visar trender över dagar, veckor, månader osv. Du kan också välja ett cirkeldiagram om du vill visa procentvärden för de visade sidorna.

**Ändra ett rapportdiagram**

1. Kör en rapport.
1. Klicka på **[!UICONTROL Configure Graph]**.
1. Markera en diagramtyp.

   **[!UICONTROL Trend Line]**: Trendlinjer visar dagliga trender för rapportmätvärden och är användbara för trendning av ett mätvärde över tid per rad.

   ![](assets/graph_trend_line.png)

   **[!UICONTROL Smooth Line]**: Du använder den här diagramtypen tillsammans med  [!UICONTROL Video Detail Report]. Den visar antalet eller procentandelen vyer för specifika segment i en video. En ökning av vyerna för ett visst segment i videon anger att tittarna har rullat tillbaka och visat det avsnittet flera gånger. Om du använder procentvärden är procentandelen som visas i diagrammet en procentandel av alla segment som visas, inte en procentandel av de tittare som såg segmentet. I diagrammet är summan av alla rapportsegment till exempel 39. Antalet vyer för segmentet 0 till 10 sekunder är 10. Procentandelen vyer för det här segmentet är därför ungefär 26 procent.

   ![](assets/graph_smooth_line.png)

   **[!UICONTROL Area]**: Ytdiagrammet liknar trendlinjediagrammet, men fyller i området nedanför linjerna. Du måste visa en trendrapport för att kunna visa ytdiagrammet.

   ![](assets/graph_area.png)

   **[!UICONTROL Stacked Area]**: Staplade ytdiagram är användbara när du trendar ett antal produkter eller kampanjer över tid. Om du till exempel trendar de fem främsta produkterna med intäkter kan du snabbt se hur mycket de totala intäkterna genererar över tiden. Du kan förfina vyn genom att använda ett sökfilter för att inkludera eller exkludera specifika produkter.

   ![](assets/graph_stacked_area.png)

   **[!UICONTROL Vertical Bar]**: Diagrammet Lodrät stapel visar relativa procentvärden för rapportmåtten.

   ![](assets/graph_vertical_bars.png)

   **[!UICONTROL Stacked Vertical Bar]**: Genom att stapla liknande objekt kan du snabbt få en bild av hur mycket ett objekt påverkar. I en [!UICONTROL Campaign Report] kan ni till exempel stapla liknande framgångsmått och se vilken kampanj som genererar störst framgång. Stapling gör det enklare att hitta kampanjer som inte är de främsta i ett mätresultat, men som är de bästa resultaten i en kombination av mätvärden.

   ![](assets/graph_stacked_vertical.png)

   **[!UICONTROL Horizontal Bar]**: Diagrammet Vågrät liggande stapel liknar diagrammet Lodrät stapel, men kolumnerna är vågräta.

   ![](assets/graph_horizontal_bar.png)

   **[!UICONTROL Stacked Horizontal Bar]**: Diagrammet Staplad vågrät liggande stapel liknar diagrammet Lodrät stapel, men kolumnerna är vågräta.

   ![](assets/graph_stacked_horizontal.png)

   **[!UICONTROL Pie]**: Cirkeldiagrammet visar de övre procentvärdena i förhållande till varandra och visar procentandelen av de valda måtten i förhållande till helheten. Du kan visa cirkeldiagrammet för rankade rapporter.

   ![](assets/graph_pie.png)

   **[!UICONTROL Scatter]**: Punktdiagrammet visar en punktbaserad visning av de mätvärden du väljer i förhållande till varandra. Med punktdiagram kan du visualisera data i två dimensioner, så att du kan identifiera vilka objekt som är avvikelser.

   ![](assets/graph_scatter.png)

   **[!UICONTROL Bubble]**: I bubbeldiagrammet visas en bubbelvisning av de mätvärden du väljer i förhållande till varandra. Bubblornas placering visar förhållandet mellan mätvärdena på den vågräta och lodräta axeln, medan storleken på bubblan visar huvudrapportens mätvärden. Med bubbeldiagram kan du visualisera data i två dimensioner, så att du kan identifiera vilka objekt som är avvikelser.

   ![](assets/graph_bubble.png)
