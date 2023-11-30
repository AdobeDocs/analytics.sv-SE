---
description: Steg för att köra de olika rapporttyperna.
title: Köra olika rapporttyper
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: 2bb3cc1ce46fc8e5f7e15291401fce1c4d8cb839
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 0%

---

# Köra olika rapporttyper

{{ra-eol}}

Du kan köra många olika typer av rapporter i Analysis Workspace. Här följer några exempel.

En fullständig lista över tillgängliga fördefinierade rapporttyper finns i [Använd färdiga rapporter](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## Köra en utfallsrapport {#task_8FD97C8260464F9DA731A93DB8F80184}

The [!UICONTROL Fallout Report] visar antalet besökare som besökte en fördefinierad sidsekvens. Här visas också konverterings- och bortfallsfrekvenser mellan varje steg.

Kolla in nya [Utfallsanalys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) i Analysis Workspace!

1. I [!UICONTROL Adobe Analytics], klicka **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. På [!UICONTROL Fallout Report] sida, klicka **[!UICONTROL Launch the Fallout Report Builder]**.

1. På [!UICONTROL Define Checkpoints] anger du de kontrollpunkter som du vill använda för rapporten.
1. Klicka på **[!UICONTROL Run Report]**.

## Köra en sidflödesrapport {#task_133E8B87C3F04DA0A42D10CBA499305B}

Sidflödesrapporter visar i vilken ordning besökarna kommer åt sidorna och navigerar på webbplatsen. Den här rapporten hjälper dig att svara

Klicka till exempel på **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Next and previous page flow]**.

## Kör en marknadsföringskanalrapport {#task_64ADED5CC75248319E06E3E029B47F78}

Marketing Channel-rapportering ger en översiktsrapport över den första och sista beröringskanalen, med standardstatistik som intäkter, order och kostnader. Med hjälp av dessa rapporter kan ni analysera hur mycket intäkter varje kanal genererar.

Se [Marknadsföringskanal](/help/components/c-marketing-channels/analyze-mc.md) hjälpsystem för mer information.

## Köra en avvikelseidentifieringsrapport {#task_4808C96327354D789C075823F5C3A049}

Du kan köra [Analys av avvikelseidentifiering och bidrag](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) endast i Analysis Workspace.

## Köra en realtidsrapport {#task_5D25929C918E40B18965222FA94176B0}

Beskriver hur du visar och tolkar realtidsrapporter.

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Realtidsrapportering innehåller två huvudrapporter - en översiktsrapport och en detaljrapport. De består av ett antal rapporter.

Se [Översikt över rapportering i realtid](/help/components/c-real-time-reporting/realtime.md) för mer information.

1. Ta en titt på **[!UICONTROL Overview]** rapportera och dess komponenter:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI-komponent </th> 
   <th class="chdeschd"> Beskrivning </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Välj Report Suite</strong></td> 
   <td class="chdesc stentry"> Visar rapportsviten som den här realtidsrapporten omfattar. Information om hur du ändrar rapportsviten finns i <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  > Konfiguration av realtidsrapporter </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Växla mellan rapporter</strong></td> 
   <td class="chdesc stentry"> Här kan du växla mellan de rapporter du har ställt in (högst 3). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Välj tidsintervall</strong></td> 
   <td class="chdesc stentry"> Här kan du välja det övergripande tidsintervallet som ska användas av alla rapporter i rapporten. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Konfigurera rapporter</strong></td> 
   <td class="chdesc stentry"> Den här kugghjulsikonlänken visas bara om du har administratörsbehörighet. Klicka på den för dig till Report Suite Manager under <span class="ignoretag"> <span class="uicontrol"> Administratörsverktyg </span>  &gt; <span class="uicontrol"> Rapportsviter </span>  &gt; <span class="uicontrol"> Redigera inställningar </span>  &gt; <span class="uicontrol"> Realtid </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Helskärmsläge</strong></td> 
   <td class="chdesc stentry"> Ikonen för helskärmsläge visas bara om bildskärmen har ett visst proportioner (16:9 eller 16:10) OCH om webbläsaren stöder det. Observera att du inte kan interagera med skärmen i helskärmsläge (tryck på <span class="uicontrol"> Esc </span> avsluta). Helskärmsläge gör inte timeout. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Site Traffic Report</strong></td> 
   <td class="chdesc stentry"> Den blå trendlinjen visar den totala trafiken för webbplatsen. X-axeln använder literala etiketter (för 15 minuter sedan, för 10 minuter sedan) förutom det aktuella värdet, som visas som ett realtidsuttryck. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Site Total Report</strong></td> 
   <td class="chdesc stentry"> Visar antalet Webbplatssummor för de senaste N minuterna i realtidsrapportens valda mått. "N" kan konfigureras med tidsintervallväljaren. <p>Pilens färg och riktning baseras på följande algoritm: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Betydande förstärkning (uppåtpil): &gt; 100 % </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Vinst (uppåtpil): mellan 5 % och 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Platt (högerpil): mellan 5 % och -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Förlust (högerpil nedåt): mellan -5 % och -100 % </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Betydande förlust (nedpil): &lt; -100 % </li> 
      </ul> </p> <p>Om platsens totala antal rapporteras i "instanser", återspeglar dessa instanser dimensionen i den primära rapportleten. Om det finns ett instansspecifikt namn (t.ex. "Sidvyer") rapporterar platsens totala namn. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Primär rapport</strong></td> 
   <td class="chdesc stentry"> Rapport för realtidsrapportens primära dimension och för dess mått. Visar en trendlinje för det elementet för det valda tidsintervallet. Måttsumman representerar summan för hela trendlinjen. Pilen anger om objektet är kraftigt uppåt, uppåt, platt, nedåt eller till stor del förlorar. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Dialogrutan Sök</strong></td> 
   <td class="chdesc stentry"> Sökningen påverkar alla rapporter. Sökningen kvarstår när du visar rapporten. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sortera efter.. Mest populära/generatorer/förlorare</strong></td> 
   <td class="chdesc stentry"> Du kan växla för att sortera efter <span class="uicontrol"> Mest populära </span>(standard), <span class="uicontrol"> Gainers </span> (dimensioner som visar störst tillväxt), och <span class="uicontrol"> Förlorare </span> (dimensioner som är nedåtgående.) <p>Här är formeln som används för att bestämma vinst eller förlust: I realtid undersöks det tidigaste urvalet och det näst senaste exemplet och en enkel beräkning av "% ändring" utförs. Om"De senaste 15 minuterna" markeras och n representerar den aktuella minuten, jämförs n-1 med n-15. I realtid görs för närvarande ingen viktning. Den aktuella minuten ignoreras eftersom den inte är fullständig och troligen ger en falsk %-ändring. </p> <p>Den här formeln är konsekvent för alla mätvärden som används i realtidsrapporten. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sekundär 1-rapport</strong></td> 
   <td class="chdesc stentry"> Visar realtidsrapporter för den andra tilldelade rapportens dimension och för måttet. <p>Den sekundära 1-rapportleten visar de fyra viktigaste kategorierna och den 5:e är en sammanställning av alla återstående värden. För varje kategori anges den totala råvyn för den kategorin. Dessutom visas summan för alla kategorier i mitten. </p> <p> När du hovrar i ett avsnitt markeras den associerade kategorin och kategoritrendlinjen visas nedanför munstycket. </p> <p> När du hovrar på ett radobjekt markeras radobjektet plus det tillhörande avsnittet och kategoritrendlinjen visas nedanför munstycket. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sekundär 2-rapport</strong></td> 
   <td class="chdesc stentry"> Visar realtidsrapporter för den tredje tilldelade rapportens dimension och för måttet. Om du placerar pekaren ovanpå objektetiketten skjuts etiketten åt höger och en trendlinje för det hovrade objektet visas. </td> 
   </tr> 
   </table>

2. Klicka på ett listobjekt i den primära rapporten för att starta **[!UICONTROL Details]** vy för det listobjektet:  ![](assets/rtr_detail_report.png)

   | **Artikeltrendrapport** | Visar trendlinjen för objektet som markerades i översiktsrapporten under de senaste N minuterna. N kan konfigureras via tidsintervallväljaren. |
   |---|---|
   | **Artikelsumma, rapport** | Visar det totala antalet mätvärden för objektet som markerades i översiktsrapporten under de senaste N minuterna. N kan konfigureras via tidsintervallväljaren. |
   | **Korrelerad sekundär 1-rapport** | Den här rapportleten liknar mycket den sekundära 1-rapporten. Den enda skillnaden är den datakälla som används för att fylla i den här rapporten: i det här exemplet visar den korrelationen (eller uppdelningen) mellan en viss sida (den som du valde i den primära rapportleten i översiktsrapporten) och de förekomster som visas. |
   | **Korrelerad sekundär rapport 2** | Den här rapportleten liknar mycket den andra rapportleten. Den enda skillnaden är den datakälla som används för att fylla i den här rapporten: i det här exemplet visar den korrelationen (eller uppdelningen) mellan en viss sida (den som du valde i den primära rapportleten i översiktsrapporten) och språkdimensionen. |
