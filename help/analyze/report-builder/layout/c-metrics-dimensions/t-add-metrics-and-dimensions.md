---
description: Lär dig hur du lägger till mått och mått i en begäran.
title: Så här lägger du till mått och mått
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Lägga till mätvärden och dimensioner

Steg för att lägga till mått och mått i en begäran.

1. Använd [!UICONTROL Request Wizard: Step 1] formulär till [Skapa databegäran](/help/analyze/report-builder/data-requests/data-requests.md)  klicka sedan på **[!UICONTROL Next]**.
1. I [!UICONTROL Request Wizard: Step 2] formulär, dubbelklicka på mätvärden eller dra dem till önskad plats.

   ![Skärmbild med begärandeguiden: Steg 2 med en pil som pekar från mätlistan till önskat sidvisningsavsnitt.](assets/adding_metrics.png)

   När du lägger till mätvärden tas de inte bort från [!UICONTROL Metrics] eftersom du kan visa mätvärden flera gånger i en begäran. Du kan t.ex. visa delsumman för mått utöver varje värde. Listan med tillgängliga mätvärden ändras dock varje gång du lägger till eller tar bort en dimension.

   Du kan bara lägga till mätvärden i [!UICONTROL Metrics] layoutavsnitt. Mätvärden läggs till i [!UICONTROL Column Label] layout som [!UICONTROL Metric Header]. Om du flyttar en [!UICONTROL Metric Header] från [!UICONTROL Column Layout] till [!UICONTROL Row Layout], visas den där och används som ett mått för en uppdelning.

   Observera att ett sökfält visas på fliken Metrisk, precis ovanför listan Metrisk.

   ![Skärmbild med sökfältet Metrics.](assets/search_bar_metric.png)

## Riktlinjer

Tänk på följande när du lägger till mått och mått.

* När du anger en sökterm uppdateras listan automatiskt med mått som har etiketter som matchar söktermen.
* Matchen är skiftlägeskänslig och motsvarar en *innehåller* sökning.
* Fullordssökningar och andra särskilda sökflaggor (börjar med, slutar med OCH, ELLER osv.) stöds inte.

Söktermen tas bort om du avslutar Request Wizard när du klickar på [!UICONTROL Finish] eller [!UICONTROL Cancel], eller gå tillbaka till Request Wizard Step 1 eller ändra kategorin Metrisk.

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

   På [!UICONTROL Dimensions] -fliken visar systemet dimensioner som bryts ned eller är en klassificering av en basrapport som du väljer på [!UICONTROL Request Wizard: Step 1]och om rapportsvitens konfiguration. När du släpper en dimension i layoutstödrastret tas den bort från trädvyn och räknar om listan med återstående tillgängliga dimensioner.

   The [!UICONTROL Date] dimension läggs till automatiskt. Tillgängliga datumdimensioner ändras beroende på vald granularitet från [!UICONTROL Request Wizard: Step 1]. Giltiga värden är:

   * Timme
   * Dag
   * Vecka
   * Månad
   * År
   * Datumintervall (när ingen granularitet har angetts)

1. Ändra mått och mått genom att konfigurera [formatalternativ](/help/analyze/report-builder/layout/t-format-display-headers.md) och filter.
1. Klicka på **[!UICONTROL Finish]**.
I följande exempel är dimensionerna relaterade till [!UICONTROL Page] mätvärden. The [!UICONTROL Referring Domain] dimension skapar en uppdelningsrapport mellan [!UICONTROL Page] och [!UICONTROL Referring Domain]. The [!UICONTROL Dimension] Fliken uppdateras endast med dimensioner som du kan lägga till i en detaljrapport.

   ![Skärmbild som visar måtten.](assets/page_pageview_02.png)
