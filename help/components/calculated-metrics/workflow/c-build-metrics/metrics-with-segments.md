---
description: Lär dig segmentera på enskilda mätvärden, vilket gör att du kan göra måttjämförelser inom samma visualisering.
title: Segmenterade mått
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Segmenterade mätvärden

I [verktyget för beräknade mätvärden](cm-build-metrics.md#definition-builder) kan du använda segment i måttdefinitionen. Det är praktiskt att använda segment om du vill använda mätvärden för en delmängd av dina data i analysen.

>[!NOTE]
>
>Segmentdefinitioner uppdateras via [segmentbyggaren](/help/components/segmentation/segmentation-workflow/seg-build.md). Om du ändrar ett segment uppdateras det automatiskt överallt där det används, inklusive om segmentet ingår i en beräknad måttdefinition.
>

Ni vill jämföra mätvärden för tyska människor som interagerar med ert varumärke med människor utanför Tyskland. Du kan alltså svara på frågor som:

1. Hur många tyska jämfört med internationella personer besöker dina mest [populära sidor](#popular-pages).
1. Hur många tyska jämfört med internationella personer på [totalt](#totals) har interagerat online med ditt varumärke den här månaden.
1. Vilka är de [procentandelarna](#percentages) tyskar och internationella personer som har besökt dina populära sidor?

Se avsnitten nedan för att illustrera hur segmenterade mätvärden kan hjälpa dig att svara på dessa frågor. Vid behov hänvisas till mer detaljerad dokumentation.

## Populära sidor

1. [Skapa ett beräknat mått](../cm-workflow.md) från ett Workspace-projekt med namnet `Germany`.
1. I [kalkylerade måttverktyget](cm-build-metrics.md) [skapar du ett segment](/help/components/segmentation/segmentation-workflow/seg-build.md), med namnet `Germany`, som använder fältet Länder.

   >[!TIP]
   >
   >I verktyget Beräknade mätvärden kan du skapa ett segment direkt med hjälp av panelen Komponenter.
   >   

   Ditt segment skulle kunna se ut som.

   ![Segmentera Tyskland](assets/segment-germany.png)

1. Använd segmentet för att uppdatera det beräknade måttet i verktyget Beräknade mått.

   ![Beräknat mätvärde Tyskland](assets/germany-visits.png)

Upprepa stegen ovan för den internationella versionen av det beräknade måttet.

1. Skapa ett beräknat mått från ditt Workspace-projekt med namnet `Non Germany visits`.
1. Skapa ett segment, med namnet `Not Germany`, som använder fältet CRM-land från dina CRM-data för att avgöra var en person kommer från i verktyget Beräknade mätvärden.

   Ditt segment ska se ut som.

   ![Segmentera Tyskland](assets/segment-not-germany.png)

1. Använd segmentet för att uppdatera det beräknade måttet i verktyget Beräknade mått.

   ![Beräknat mätvärde Tyskland](assets/non-germany-visits.png)


1. Skapa ett projekt i Analysis Workspace där du tittar på sidor som besökts av tyska och icke-tyska besökare.

   ![Workspace Freeform-tabellvisualisering som visar tyska kontra internationella personer](assets/workspace-german-vs-international.png)


## Summor

1. Skapa två nya beräknade värden baserade på totalsumman. Öppna varje segment som skapats tidigare, byt namn på segmentet, ange **[!UICONTROL Metric type]** för **[!UICONTROL People]** till **[!UICONTROL Grand Total]** och använd **[!UICONTROL Save As]** för att spara segmentet med det nya namnet. Exempel:

   ![Totalt mått för Tyskland](assets/calculated-metric-germany-total.png)

1. Lägg till en ny visualisering av Freeform-tabeller i ditt Workspace-projekt, med årets totala sidor.

   ![Workspace Freeform-tabellvisualisering som visar totalt antal tyska och internationella personer](assets/workspace-german-vs-international-totals.png)


## Procenttal

1. Skapa två nya beräknade mätvärden som beräknar en procentandel av de beräknade mätvärden som du skapade tidigare.

   ![Visualisering av Workspace Freeform-tabell som visar det totala antalet tyska jämfört med internationella personer i procent](assets/calculated-metric-germany-total-percentage.png)


1. Uppdatera ditt Workspace-projekt.

   ![Workspace Freeform-tabellvisualisering som visar totalt antal tyska och internationella personer](assets/workspace-german-vs-international-totals-percentage.png)

