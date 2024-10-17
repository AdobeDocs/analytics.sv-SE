---
description: Lär dig hur du lägger till mått och mått i en begäran.
title: Så här lägger du till mått och mått
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Lägg till mått och mått

{{legacy-arb}}

Steg för att lägga till mått och mått i en begäran.

1. Använd formuläret [!UICONTROL Request Wizard: Step 1] för att [skapa databegäran](/help/analyze/legacy-report-builder/data-requests/data-requests.md) och klicka sedan på **[!UICONTROL Next]**.
1. Dubbelklicka på mätvärden i formuläret [!UICONTROL Request Wizard: Step 2] eller dra dem till önskad plats.

   ![Skärmbild med begärandeguiden: Steg 2 med en pil som pekar från mätlistan till önskat sidvisningsavsnitt.](assets/adding_metrics.png)

   När du lägger till mått tas de inte bort från fliken [!UICONTROL Metrics] eftersom du kan visa mått flera gånger i en begäran. Du kan t.ex. visa delsumman för mätvärden utöver varje värde. Listan med tillgängliga mätvärden ändras dock varje gång du lägger till eller tar bort en dimension.

   Du kan bara lägga till mått i layoutavsnittet [!UICONTROL Metrics]. Mått läggs till i layouten [!UICONTROL Column Label] som en [!UICONTROL Metric Header]. Om du flyttar en [!UICONTROL Metric Header] från [!UICONTROL Column Layout] till [!UICONTROL Row Layout] visas den där och används som ett mått som en nedbrytning.

   Observera att ett sökfält visas på fliken Metrisk, precis ovanför listan Metrisk.

   ![Skärmbild som visar sökfältet Metrics.](assets/search_bar_metric.png)

## Riktlinjer

Tänk på följande när du lägger till mått och mått.

* När du anger en sökterm uppdateras listan automatiskt med mått som har etiketter som matchar söktermen.
* Matchningen är inte skiftlägeskänslig och motsvarar en *innehåller*-sökning.
* Fullordssökningar och andra särskilda sökflaggor (börjar med, slutar med OCH, ELLER osv.) stöds inte.

Söktermen tas bort om du avslutar Request Wizard när du klickar på [!UICONTROL Finish] eller [!UICONTROL Cancel], eller går tillbaka till Request Wizard Step 1, eller ändrar kategorin Metrisk.

Söktermen är inte rensad:

* När du drar (eller dubbelklickar) ett måttobjekt från listan så att det läggs till på panelen Pivottayout/Anpassade layoutmått.
* När du tar bort ett eller flera måttobjekt från panelen Pivotlayout/Anpassade mått för layout.
* När du klickar på fliken Dimension går du tillbaka till fliken Metrisk.
* När du anropar andra delformulär (modala eller modelllösa) återgår det när du avslutar till begärandeguiden steg 2. Exempel på dessa formulär är

   * Dimension Filter Forms
   * Forms för datumintervallformatering
   * Formulär för formatalternativ
   * Textformulär för prepend-post
   * Formulär för plats för utdataområde

## Sortera en begäran efter mått

Du kan sortera en begäran efter mätvärden.

Så här sorterar du en begäran efter mått

1. Klicka på måttetiketten.
1. Lägg till dimensioner. Lägg till dimensioner på samma sätt som du lägger till mätvärden. Se steg 1 och 2 ovan.

   På fliken [!UICONTROL Dimensions] visar systemet dimensioner som bryts ned eller som är en klassificering av en basrapport som du väljer på [!UICONTROL Request Wizard: Step 1] och på konfigurationen av rapportsviten. När du släpper en dimension i layoutstödrastret tas den bort från trädvyn och räknar om listan med återstående tillgängliga dimensioner.

   Dimensionen [!UICONTROL Date] läggs till automatiskt. Tillgängliga datumdimensioner ändras beroende på den valda granulariteten från [!UICONTROL Request Wizard: Step 1]. Giltiga värden är:

   * Timme
   * Dag
   * Vecka
   * Månad
   * År
   * Datumintervall (när ingen granularitet har angetts)

1. Ändra mått och mått genom att konfigurera [formatalternativ](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md) och filter.
1. Klicka på **[!UICONTROL Finish]**.
I följande exempel är dimensionerna relaterade till måttet [!UICONTROL Page]. Dimensionen [!UICONTROL Referring Domain] skapar en detaljrapport mellan [!UICONTROL Page] och [!UICONTROL Referring Domain]. Fliken [!UICONTROL Dimension] uppdateras endast med dimensioner som du kan lägga till i en detaljrapport.

   ![Skärmbild som visar dimensionerna som relaterar till måttet.](assets/page_pageview_02.png)
