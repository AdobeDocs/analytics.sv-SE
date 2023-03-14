---
description: Steg för att lägga till mått och mått i en begäran.
title: Lägga till mätvärden och dimensioner
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 1%

---

# Lägga till mätvärden och dimensioner

Steg för att lägga till mått och mått i en begäran.

1. [Skapa databegäran](/help/analyze/report-builder/data-requests/data-requests.md) på [!UICONTROL Request Wizard: Step 1]och sedan klicka **[!UICONTROL Next]**.
1. På [!UICONTROL Request Wizard: Step 2], dubbelklicka på mätvärden eller dra dem till önskad plats.

   ![Steginformation](assets/adding_metrics.png)

   När du lägger till mätvärden tas de inte bort från [!UICONTROL Metrics] eftersom du kan visa mätvärden flera gånger i en begäran. Du kan t.ex. visa delsumman för mått utöver varje värde. Listan med tillgängliga mätvärden ändras dock varje gång du lägger till eller tar bort en dimension.

   Du kan bara lägga till mått i [!UICONTROL Metrics] layoutavsnitt. Mätvärden läggs till i [!UICONTROL Column Label] layout som [!UICONTROL Metric Header]. Om du flyttar en [!UICONTROL Metric Header] från [!UICONTROL Column Layout] till [!UICONTROL Row Layout], visas den där och används som ett mått för en uppdelning.

   Observera att ett sökfält visas på fliken Metrisk, precis ovanför listan Metrisk.

   ![](assets/search_bar_metric.png)

   Tänk på detta:

   * När du anger en sökterm uppdateras listan automatiskt så att endast de mått vars etikett matchar söktermen visas.
   * Matchningen är inte skiftlägeskänslig och motsvarar en&quot;innehåller&quot;-sökning.
   * Fullordssökningar eller annan särskild sökflagga (börjar med, slutar med OCH, ELLER osv.) stöds inte.

      Söktermen kommer att rensas om du avslutar Request Wizard (d.v.s. klickar på Finish (Slutför) eller Cancel), eller går tillbaka till Request Wizard Step 1, eller ändrar kategorin Metric.

      Söktermen kommer inte att rensas i följande fall:

   * Du kan dra och släppa (eller dubbelklicka) ett av måttobjekten från listan så att det läggs till på panelen Pivottayout/Anpassade layoutmått.
   * Du tar bort ett eller flera måttobjekt från panelen Pivottext/Anpassade layoutmått.
   * Klicka på fliken Dimension och gå sedan tillbaka till fliken Metrisk.
   * Du anropar andra delformulär (modala eller modelllösa) som när du avslutar kommer att återgå till begärandeguiden steg 2. Exempel på dessa formulär är

      * Dimension Filter Forms
      * Forms för datumintervallformatering
      * Formulär för formatalternativ
      * Textformulär för att lägga till
      * Formulär för plats för utdataområde

1. (Valfritt) Om du vill sortera en begäran efter mått klickar du bara på måttetiketten.
1. Lägg till dimensioner på samma sätt som du lägger till mätvärden.

På [!UICONTROL Dimensions] visas dimensioner som bryts ned eller är en klassificering av en basrapport som du väljer i steg 1, och på rapportsvitens konfiguration. När du släpper en dimension i layoutstödrastret tas den bort från trädvyn och räknar om listan med återstående tillgängliga dimensioner.

The [!UICONTROL Date] dimension läggs till automatiskt. Tillgängliga datumdimensioner ändras beroende på vald granularitet från [!UICONTROL Request Wizard: Step 1]. (Giltiga värden är:

    * Timme
    * Dag
    * Vecka
    * Månad
    * År
    * Datumintervall (när ingen granularitet har angetts)

1. Ändra mått och mått genom att konfigurera [formatalternativ](/help/analyze/report-builder/layout/t-format-display-headers.md) och filter.
1. Klicka på **[!UICONTROL Finish]**.
I följande exempel är dimensionerna relaterade till [!UICONTROL Page] mätvärden. Här är [!UICONTROL Referring Domain] dimension skapar en uppdelningsrapport mellan [!UICONTROL Page] och [!UICONTROL Referring Domain]. The [!UICONTROL Dimension] -fliken uppdateras endast med dimensioner som du kan lägga till i en detaljrapport.

![](assets/page_pageview_02.png)
