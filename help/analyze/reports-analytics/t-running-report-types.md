---
description: Steg för att köra de olika rapporttyperna.
title: Köra olika rapporttyper
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: d6430845f30a5b14c29c3c4111bf9c60a69eeea4
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# Köra olika rapporttyper

Steg för att köra de olika rapporttyperna.

## Kör en rankad rapport {#task_C570BA4A213F4F2EB7B30E012934BE7D}

I en rankad rapport visar tabellen rangordningarna av rapportsidorna i förhållande till måttet, utifrån antal eller procent. Rankade rapporter kan visa flera mätvärden i en rapport.

1. Generera en rapport, till exempel en [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**).
1. Klicka på **[!UICONTROL Ranked.]** i rapportrubriken
1. Om du vill rangordna rapporten klickar du på en kolumnrubrik i tabellen.

   Rankade rapporter kan innehålla upp till 200 artiklar som listas i tabellen (t.ex. produkter, kategorier, webbsidor) och tio siffror (intäkter, order, vyer osv.).

## Köra en trendrapport {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trendrapporter visar mätvärden över tid. Du använder den här rapporttypen när du vill se hur ett segment fungerar från en tidsperiod till nästa.

De flesta konverterings- och trafikrapporter har en trendvy tillgänglig. Med [!UICONTROL Calendar] kan du visa förbättring för alla delningar av tidsperioder, t.ex. dagar i en månad, veckor i ett år, veckor i ett kvartal, månader i ett år o.s.v. Trendrapporter visar trender för ett enskilt mått (intäkter, order, vyer och så vidare) för upp till fem artiklar (som produkter, kategorier, webbsidor och så vidare).

**Köra en trendrapport**

1. Kör en konverterings- eller trafikrapport, till exempel **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]** klickar du på **[!UICONTROL Trended.]**

## Köra en utfallsrapport {#task_8FD97C8260464F9DA731A93DB8F80184}

I [!UICONTROL Fallout Report] visas antalet besökare som besökt en fördefinierad sidsekvens. Här visas också konverterings- och bortfallsfrekvenser mellan varje steg.

Kolla in den nya panelen [Bortfallsanalys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) i Analysis Workspace!

1. I [!UICONTROL Adobe Analytics] klickar du på **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. Klicka på **[!UICONTROL Launch the Fallout Report Builder]** på sidan [!UICONTROL Fallout Report].

   ![Stegresultat](assets/fallout_add_items.png)

1. På sidan [!UICONTROL Define Checkpoints] anger du de kontrollpunkter som du vill använda för rapporten.
1. Klicka på **[!UICONTROL Run Report]**.

   ![Stegresultat](assets/fallout_report.png)

## Köra en sidflödesrapport {#task_133E8B87C3F04DA0A42D10CBA499305B}

Sidflödesrapporter visar i vilken ordning besökarna kommer åt sidorna och navigerar på webbplatsen. Den här rapporten hjälper dig att svara

Ta en titt på [Flödesvisualisering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) i Analysis Workspace!

Klicka till exempel på **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**.

## Kör en marknadsföringskanalrapport {#task_64ADED5CC75248319E06E3E029B47F78}

Marketing Channel-rapportering ger en översiktsrapport över den första och sista beröringskanalen, med standardstatistik som intäkter, order och kostnader. Med hjälp av dessa rapporter kan ni analysera hur mycket intäkter varje kanal genererar.

Mer information finns i hjälpsystemet [Marketing Channel](/help/components/c-marketing-channels/analyze-mc.md).

## Köra en avvikelseidentifieringsrapport {#task_4808C96327354D789C075823F5C3A049}

Du kan bara köra [Analys av avvikelseidentifiering och bidragsanalys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) i Analysis Workspace.

## Köra en realtidsrapport {#task_5D25929C918E40B18965222FA94176B0}

Beskriver hur du visar och tolkar realtidsrapporter.

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Realtidsrapportering innehåller två huvudrapporter - en översiktsrapport och en detaljrapport. De består av ett antal rapporter.

Mer information finns i [Översikt över realtidsrapportering](/help/components/c-real-time-reporting/realtime.md).

1. Ta en titt på **[!UICONTROL Overview]**-rapporten och dess komponenter:  ![](assets/rtr_overview_report.png)

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
   <td class="chdesc stentry"> Den här kugghjulsikonlänken visas bara om du har administratörsbehörighet. Om du klickar på den öppnas Report Suite Manager under <span class="ignoretag"> <span class="uicontrol"> Admin Tools </span> &gt; <span class="uicontrol"> Report Suites </span> &gt; <span class="uicontrol"> Edit Settings </span> &gt; <span class="uicontrol"> Real-Time </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Helskärmsläge</strong></td> 
   <td class="chdesc stentry"> Ikonen för helskärmsläge visas bara om bildskärmen har ett visst proportioner (16:9 eller 16:10) OCH om webbläsaren stöder det. Observera att du inte kan interagera med skärmen när den är i helskärmsläge (tryck på <span class="uicontrol"> Esc </span> för att avsluta). Helskärmsläge gör inte timeout. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Platstrafikrapport</strong></td> 
   <td class="chdesc stentry"> Den blå trendlinjen visar den totala trafiken för webbplatsen. X-axeln använder literala etiketter (för 15 minuter sedan, för 10 minuter sedan) förutom det aktuella värdet, som visas som ett realtidsuttryck. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Site Total Report</strong></td> 
   <td class="chdesc stentry"> Visar antalet Webbplatssummor för de senaste N minuterna i realtidsrapportens valda mått. "N" kan konfigureras med tidsintervallväljaren. <p>Pilens färg och riktning baseras på följande algoritm: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Betydande förstärkning (uppåtpil): &gt; 100 % </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Vinst (uppåthögerpil): mellan 5 % och 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Platt (högerpil): mellan 5 % och -5 % </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Förlust (högerpil nedåt): mellan -5 % och -100 % </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Betydande förlust (nedpil): &lt; -100% </li> 
      </ul> </p> <p>Om platsens totala antal rapporteras i "instanser", återspeglar dessa instanser dimensionen i den primära rapportleten. Om det finns ett instansspecifikt namn (t.ex. "Sidvyer") rapporterar platsens totala namn. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Primär rapportlet</strong></td> 
   <td class="chdesc stentry"> Rapport för realtidsrapportens primära dimension och för dess mått. Visar en trendlinje för det elementet för det valda tidsintervallet. Måttsumman representerar summan för hela trendlinjen. Pilen anger om objektet är kraftigt uppåt, uppåt, platt, nedåt eller till stor del förlorar. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Dialogrutan Sök</strong></td> 
   <td class="chdesc stentry"> Sökningen påverkar alla rapporter. Sökningen kvarstår när du visar rapporten. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sortera efter.. Mest populära/generatorer/förlorare</strong></td> 
   <td class="chdesc stentry"> Du kan växla till att sortera efter <span class="uicontrol"> Popular </span> (standard), <span class="uicontrol"> Gainers </span> (mått som visar störst tillväxt) och <span class="uicontrol"> Losers </span> (dimensioner som finns på en nedåtriktad projektbana). <p>Här är formeln som används för att bestämma vinjetter eller förlorare: I realtid undersöks det tidigaste exemplet och det näst senaste exemplet och en enkel beräkning av "% change" utförs. Om"De senaste 15 minuterna" markeras och n representerar den aktuella minuten, jämförs n-1 med n-15. I realtid görs för närvarande ingen viktning. Den aktuella minuten ignoreras eftersom den inte är fullständig och troligen ger en falsk %-ändring. </p> <p>Den här formeln är konsekvent för alla mätvärden som används i realtidsrapporten. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sekundär 1-rapport</strong></td> 
   <td class="chdesc stentry"> Visar realtidsrapporter för den andra tilldelade rapportens dimension och för måttet. <p>I den sekundära rapportletten visas de fyra viktigaste kategorierna. det femte är en sammanställning av alla återstående värden. För varje kategori anges den totala råvyn för den kategorin. Dessutom visas summan för alla kategorier i mitten. </p> <p> När du hovrar i ett avsnitt markeras den associerade kategorin och kategoritrendlinjen visas nedanför munstycket. </p> <p> När du hovrar på ett radobjekt markeras radobjektet plus det tillhörande avsnittet och kategoritrendlinjen visas nedanför munstycket. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sekundär 2-rapport</strong></td> 
   <td class="chdesc stentry"> Visar realtidsrapporter för den tredje tilldelade rapportens dimension och för måttet. Om du placerar pekaren ovanpå objektetiketten skjuts etiketten åt höger och en trendlinje för det hovrade objektet visas. </td> 
   </tr> 
   </table>

2. Klicka på ett listobjekt i den primära rapporten för att starta vyn **[!UICONTROL Details]** för det listobjektet:  ![](assets/rtr_detail_report.png)

   | **Artikeltrendrapport** | Visar trendlinjen för objektet som markerades i översiktsrapporten under de senaste N minuterna. N kan konfigureras via tidsintervallväljaren. |
   |---|---|
   | **Artikelsumma, rapport** | Visar det totala antalet mätvärden för objektet som markerades i översiktsrapporten under de senaste N minuterna. N kan konfigureras via tidsintervallväljaren. |
   | **Korrelerad sekundär 1-rapport** | Den här rapportleten liknar mycket den sekundära 1-rapporten. Den enda skillnaden är den datakälla som används för att fylla i den här rapporten: I det här exemplet visar det korrelationen (eller uppdelningen) mellan en viss sida (den som du valde i den primära rapportleten i översiktsrapporten) och de förekomster som visas. |
   | **Korrelerad sekundär rapport 2** | Den här rapportleten liknar mycket den andra rapportleten. Den enda skillnaden är den datakälla som används för att fylla i den här rapporten: I det här exemplet visar det korrelationen (eller uppdelningen) mellan en viss sida (den du valde i den primära rapportleten i översiktsrapporten) och språkdimensionen. |
