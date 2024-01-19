---
description: Steg som beskriver hur du anpassar diagrammet så att det är mest användbart för den avsedda målgruppen.
title: Ändra rapportdiagram
uuid: c2e81c6c-bfe9-4457-8b5d-512255ca9711
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a098b38-0939-4dd2-9a05-1b6b678f2d50
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Ändra rapportdiagram

{{ra-eol}}

Du kan anpassa diagrammet så att det passar den avsedda målgruppen bäst.

Vilken typ av diagram som är tillgängliga beror på vilken typ av rapport du kör. Trend Line-diagram är till exempel användbara för trendrapporter, men du kan också använda ett vertikalt liggande diagram med trendlinjer som tydligt visar trender över dagar, veckor, månader osv. Du kan också välja ett cirkeldiagram om du vill visa procentvärden för de visade sidorna.

Så här ändrar du ett rapportdiagram:

1. Kör en rapport.
1. Klicka på **[!UICONTROL Configure Graph]**.
1. Markera en diagramtyp.

   **[!UICONTROL Trend Line]**: Trendlinjer visar dagliga trender för rapportens mätvärden och är användbara för trendning av ett mätresultat över tid per rad.

   ![](assets/graph_trend_line.png)

   **[!UICONTROL Smooth Line]**: Du använder den här diagramtypen med [!UICONTROL Video Detail Report]. Den visar antalet eller procentandelen vyer för specifika segment i en video. En ökning av vyerna för ett visst segment i videon indikerar att tittarna har rullat tillbaka och visat det avsnittet flera gånger. Om du använder procentvärden är procentandelen som visas i diagrammet en procentandel av alla segment som visas, inte en procentandel av de tittare som såg segmentet. I diagrammet är summan av alla rapportsegment till exempel 39. Antalet vyer för segmentet 0 till 10 sekunder är 10. Procentandelen vyer för det här segmentet är därför ungefär 26 procent.

   ![](assets/graph_smooth_line.png)

   **[!UICONTROL Area]**: Ytdiagrammet liknar trendlinjediagrammet, men fyller i området nedanför linjerna. Du måste visa en trendrapport för att kunna visa ytdiagrammet.

   ![](assets/graph_area.png)

   **[!UICONTROL Stacked Area]**: Staplade ytdiagram är användbara när du trendar ett antal produkter eller kampanjer över tid. Om du till exempel trendar de fem främsta produkterna med intäkter kan du snabbt se hur mycket de totala intäkterna genererar över tiden. Du kan förfina vyn genom att använda ett sökfilter för att inkludera eller exkludera specifika produkter.

   ![](assets/graph_stacked_area.png)

   **[!UICONTROL Vertical Bar]**: Diagrammet Lodrät stapel visar relativa procentvärden för rapportmåtten.

   ![](assets/graph_vertical_bars.png)

   **[!UICONTROL Stacked Vertical Bar]**: Genom att stapla liknande objekt kan du snabbt få en bild av hur mycket ett objekt påverkar. I en [!UICONTROL Campaign Report]kan ni stapla liknande framgångsvärden och se vilken kampanj som genererar störst framgång. Stapling gör det enklare att hitta kampanjer som inte är de främsta i ett mätresultat, men som är de bästa resultaten i en kombination av mätvärden.

   ![](assets/graph_stacked_vertical.png)

   **[!UICONTROL Horizontal Bar]**: Det vågräta stapeldiagrammet liknar det lodräta stapeldiagrammet, men kolumnerna är vågräta.

   ![](assets/graph_horizontal_bar.png)

   **[!UICONTROL Stacked Horizontal Bar]**: Diagrammet Staplad vågrät liggande stapel liknar diagrammet Lodrät stapel, men kolumnerna är vågräta.

   ![](assets/graph_stacked_horizontal.png)

   **[!UICONTROL Pie]**: Cirkeldiagrammet visar de övre måttvärdesprocenten i förhållande till varandra och visar procentandelen av de valda måtten i förhållande till helheten. Du kan visa cirkeldiagrammet för rankade rapporter.

   ![](assets/graph_pie.png)

   **[!UICONTROL Scatter]**: Spridningsdiagrammet visar en punktvisning av de värden du väljer i förhållande till varandra. Med punktdiagram kan du visualisera data i två dimensioner, så att du kan identifiera vilka objekt som är avvikelser.

   ![](assets/graph_scatter.png)

   **[!UICONTROL Bubble]**: Bubbeldiagrammet visar en bubbelvisning av de mätvärden du väljer i förhållande till varandra. Bubblornas placering visar förhållandet mellan mätvärdena på den vågräta och lodräta axeln, medan storleken på bubblan visar huvudrapportens mätvärden. Med bubbeldiagram kan du visualisera data i två dimensioner, så att du kan identifiera vilka objekt som är avvikelser.

   ![](assets/graph_bubble.png)
