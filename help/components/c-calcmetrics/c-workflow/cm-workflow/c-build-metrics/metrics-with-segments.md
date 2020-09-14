---
description: 'Genom att segmentera enskilda mätvärden kan ni göra mätjämförelser inom samma rapport. '
title: Segmenterade mätvärden
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 234a2eadfe02322daa886d2edbea042f8ad99e1e
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---


# Segmenterade mätvärden

I verktyget Beräknade mätvärden kan du använda segment i måttdefinitionen. Detta är praktiskt om du vill ta fram nya mätvärden som ska användas i din analys. Tänk på att segmentdefinitioner kan uppdateras med segmentverktyget. Om ändringar görs uppdateras segmentet automatiskt varhelst det används, inklusive om det ingår i en beräknad måttdefinition.

![](assets/german-visitors.png)

## Skapa ett segmenterat mätresultat {#create}

Låt oss säga att du vill jämföra olika aspekter av ett&quot;tyska besökarsegment&quot; med ett&quot;internationellt besökarsegment&quot;. Du kan skapa mätvärden som ger dig insikter som:

* Hur fungerar innehållssökning jämfört med de två grupperna? (Ett annat exempel är: Hur skiljer sig konverteringsgraden mellan de två segmenten?)
* Hur många tyska besökare surfar på vissa sidor jämfört med internationella besökare som en procentandel av det totala antalet besökare?
* Var är de största skillnaderna när det gäller vilket innehåll som nås av de olika segmenten?

1. Om du inte har något jämförbart segment skapar du ett ad hoc-segment direkt i Calculated Metric Builder som heter&quot;Tyska besökare&quot;, där&quot;Länder&quot; är lika med&quot;Tyskland&quot;. Dra bara dimensionen Länder till arbetsytan Definition och välj Tyskland som värde:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Du kan också göra detta i [Segmentverktyget](/help/components/segmentation/segmentation-workflow/seg-build.md), men vi har förenklat arbetsflödet genom att göra dimensioner tillgängliga i verktyget Beräknad metrisk. &quot;Adhoc&quot; innebär att segmentet inte är synligt i listan i den vänstra listen **[!UICONTROL Segments]** . Du kan emellertid göra den offentlig genom att hålla muspekaren över ikonen&quot;i&quot; bredvid den och klicka **[!UICONTROL Make public]**.

1. Om du inte har något jämförbart segment skapar du ett segment som kallas&quot;Internationella besökare&quot; där&quot;Länder&quot; inte är lika med&quot;Tyskland&quot;.
1. Bygg och spara ett mätvärde som kallas&quot;tyska besökare&quot; genom att dra segmentet Tyskland till arbetsytan Definition och dra det unika besökarmåttet i det:

   ![](assets/german-visitors.png)

1. Upprepa steg 3 med segmentet Internationell besökare och mätvärdet Unik besökare för att skapa ett internationellt besökarmått.
1. I Analysis Workspace drar du **[!UICONTROL Page]** Dimensionen till en frihandstabell och drar de två nya beräknade måtten till varandra högst upp:

   ![](assets/workspace-pages.png)

## Procent av totala mätvärden {#percent-total}

Du kan ta exemplet ovan ett steg längre genom att jämföra segmentet med en total population. Det gör du genom att skapa två nya mätvärden, &quot;% av totalt antal tyska besökare&quot; och &quot;% av totalt antal internationella besökare&quot;:

1. Släpp segmentet med tyska (eller internationella) besökare på arbetsytan.
1. Släpp ytterligare tyska (eller internationella) besökare nedan. Men den här gången klickar du på konfigurationsikonen (kugghjulsikonen) för att välja måtttypen &quot;Totalt&quot;. Formatet ska vara &quot;Procent&quot;. Operatorn ska delas med. Resultatet blir den här måttdefinitionen:

   ![](assets/cm_metric_total.png)

1. Använd följande mått i ditt projekt:

   ![](assets/cm_percent_total.png)

