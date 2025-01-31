---
description: Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.
keywords: Analysis Workspace;Synkronisera visualisering med datakälla
title: Hantera datakällor för visualisering
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Hantera datakällor för visualisering

Med synkronisering av visualiseringar kan du styra vilken datatabell eller datakälla som motsvarar en visualisering.

**Tips!** Du kan se vilka visualiseringar som är relaterade till färgen på punkten bredvid titeln. Matchande färger innebär att visualiseringar baseras på samma datakälla.

Genom att hantera en datakälla kan du visa datakällan eller låsa markeringen. Dessa inställningar avgör hur visualiseringen ändras (eller inte ändras) när nya data kommer in.

1. [Skapa ett projekt](/help/analyze/analysis-workspace/home.md) med en datatabell och en [visualisering](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Markera cellerna (datakällan) som du vill koppla till visualiseringen i datatabellen.
1. I visualiseringen klickar du på punkten bredvid titeln för att öppna dialogrutan **[!UICONTROL Data Source]**. Välj **[!UICONTROL Show Data Source]** eller **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synkronisering av en visualisering till en tabellcell skapar en ny (dold) tabell och färgkodar den synkroniserade visualiseringen med den tabellen.

## Inställningar för Data Source


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Datakällinställningar](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


| Element | Beskrivning |
| --- | --- |
| Länkade visualiseringar | Om det finns visualiseringar kopplade till en frihands- eller kohorttabell öppnas den övre vänstra punkten för att visa de anslutna visualiseringarna och har kryssrutan &quot;visa&quot; för att visa/dölja tabellen. När du hovrar markeras den länkade visualiseringen och du klickar på den. |
| Visa data i Source | Gör att du kan visa (genom att aktivera kryssrutan) eller dölja (genom att inaktivera) den datatabell som motsvarar visualiseringen. |
| Lås markering | Aktivera den här inställningen för att låsa visualiseringen till de data som är markerade i motsvarande datatabell. När det är aktiverat väljer du mellan:<ul><li>**Markerade positioner**: Välj det här alternativet om du vill att visualiseringen ska förbli låst på de positioner som är markerade i motsvarande datatabell. Dessa positioner fortsätter att visualiseras, även om de specifika objekten i de här positionerna ändras. Välj till exempel det här alternativet om du alltid vill visa de fem främsta kampanjnamnen i den här visualiseringen, oavsett vilka kampanjnamn som visas i de fem främsta.</li><li>**Markerade objekt**: Välj det här alternativet om du vill att visualiseringen ska förbli låst för de specifika objekt som är markerade i motsvarande datatabell. Dessa objekt fortsätter att visualiseras, även om de ändrar sin rankning bland objekt i tabellen. Välj till exempel det här alternativet om du alltid vill visa samma fem specifika kampanjnamn i den här visualiseringen, oavsett var kampanjnamnen rangordnas.</li></ul> |

Arkitekturen skiljer sig från den tidigare på så sätt att Analysis Workspace inte längre skapar en dold tabell som lagrar den låsta markeringen åt dig. Datakällan pekar nu på tabellen som du skapade visualiseringen från.

## Exempel på användningsområden

* Du kan skapa en sammanfattningsvisualisering och låsa den till en cell i tabellen som du skapade den från. När du aktiverar&quot;Visa data-Source&quot; visas exakt var informationen kommer från i tabellen. Källdata är nedtonade:

  ![](assets/data-source2.png)>
* Du kan lägga till många visualiseringar och hämta dem från olika celler i samma tabell, vilket visas här. Tabellen är densamma som i exemplet ovan, men källcellen (och måttet) är annorlunda:

  ![](assets/data-source3.png)>
* Du kan se om det finns några visualiseringar kopplade till en frihand- eller kohorttabell genom att klicka på den övre vänstra punkten (Data Source Settings). När du hovrar markeras den länkade visualiseringen och du klickar på den.

  ![](assets/linked-visualizations.png)>
