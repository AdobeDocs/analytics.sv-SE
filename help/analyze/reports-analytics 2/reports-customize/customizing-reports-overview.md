---
description: När du har kört en rapport kan du anpassa rapporten för att visa och analysera data efter dina behov. Du kan filtrera rapportdata, ändra hur data presenteras grafiskt, ändra granularitet för datum och så vidare.
title: Anpassa rapportöversikt
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 2%

---

# Anpassa rapporter

När du har kört en rapport kan du anpassa rapporten för att visa och analysera data efter dina behov. Du kan filtrera rapportdata, ändra hur data presenteras grafiskt, ändra granularitet för datum och så vidare.

## Välj ett datum eller datumintervall {#task_9BEF7D4D839A4748B76E8500D1406C34}

Du kan välja tidsperioder för rapportdata.

<!-- 

t_reports_select_date.xml

 -->

Du kan välja specifika dagar, veckor, månader eller år. Du kan också köra jämförelserapporter.

När du öppnar en kontrollpanel med rapporter som har olika datumintervall kan du välja ett nytt datumintervall i kalendern. Ändringarna gäller för alla rapporter på kontrollpanelen.

Så här väljer du ett datumintervall:

1. Kör en rapport.
1. Klicka på kalenderikonen högst upp till höger.
1. Välj ett datum.

   Ni kan:

   * Visa dagar, månader eller årsperioder (upp till tre).
   * Dra markören över datum för att markera ett intervall.
   * Ange datum manuellt.
   * Klicka på ett månadsnamn för att välja en månad.
   * Klicka **[!UICONTROL Select Preset]** för att välja ett förinställt datum.
   * Jämför datum.

1. Klicka på **[!UICONTROL Run Report]**.

## Jämför datum {#task_95155C3700774B709F5FB81AE96B0824}

Du kan använda kalendern för att köra datumjämförelser mellan rankade rapporter.

<!-- 

t_reports_comparing_dates.xml

 -->

Du kan inte jämföra datum mellan trendrapporter.

>[!NOTE]
>
>Om du vill göra en datumjämförelse av nyckeltal i en kontrollpanel kan du hämta data till [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) med två olika förfrågningar. Du kan sedan använda egna formler i Excel för att analysera skillnaden mellan de två formlerna.

<!-- delete this procedure, but what about this entire "Compare dates" section?

To compare dates between ranked reports in Reports & analytics: 

1. Run a report.
1. Click the calendar at the top right.
1. Click **[!UICONTROL Compare Dates]**.
1. Select the dates you want to use.
1. Click **[!UICONTROL Run Report]**.

-->

## Visa ett procentvärde som ett diagram {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Du kan ange om procentandelen i en rapporttabell ska visas som ett diagram.

<!-- 

t_reports_graph_percent.xml

 -->

Den här visualiseringen är även tillgänglig i rapportlets på kontrollpanelen.

Så här visar du procentandelen som ett diagram i en rapporttabell:

1. Kör en rapport som stöder procentsatser, till exempel en [!UICONTROL Pages Report].
1. Klicka på **[!UICONTROL Percent Shown As: Graph]**.

## Normalisera rapportdata {#task_8005B55E59BD479DA67BC618FF8BC94A}

<!-- 

t_reports_normalize.xml

 -->

När du har kört en rapport med jämförda datum, eller för A/B-jämförelser, kan du normalisera data för att visa procentandelen av förändring mellan rapporterna. Den sekundära datauppsättningen justeras för att kompensera för skillnader i antalet valda dagar eller för olika trafikvolymer.

Så här normaliserar du rapportdata:

1. Kör en rapport som stöder datumjämförelser.
1. Klicka **[!UICONTROL Compare Dates]** anger du sedan din datumjämförelse.
1. Klicka på **[!UICONTROL Run Report]**.
1. Klicka på **[!UICONTROL Normalize Data: Yes]**.

## Välj en sida för en rapport {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Så här väljer du en viss sida på webbplatsens sidor för en rapport:

<!-- 

t_reports_select_page.xml

 -->

1. Generera en rapport, till exempel en [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Klicka på **[!UICONTROL Selected Page]** länk.
1. På [!UICONTROL Choose Page]markerar du de sidor som du vill visa.
1. Leta reda på sidan.
1. Klicka **[!UICONTROL OK.]**

## Jämför rapportsviter {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Du kan visa rapporter från två rapportsviter i samma rapport.

<!-- 

t_reports_compare_suites.xml

 -->

Förutom den grafiska visningen ger tabellen i rapporten en procentuell jämförelse. Följande rapporter kan köras med jämförelser:

* Webbplatsinnehåll
* Mobil
* Trafikkällor
* Kampanjer
* Produkter
* Kvarhållning av besökare
* Besökarprofil
* Anpassad konvertering
* Anpassad trafik
* Target
* Undersökning

Så här jämför du rapportsviter:

1. Generera en rapport som gör att du kan jämföra rapporter.
1. Klicka på **[!UICONTROL Compare to Site]** länk.
1. Hitta rapportsviten.
1. Klicka **[!UICONTROL OK.]**

## Ange rapportgranularitet {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Du kan visa rapportsummorna varje timme, dag, vecka, månad, kvartal eller år.

<!-- 

t_reports_granularity.xml

 -->

Rapportens tidsperiod avgör vilka granularitetsalternativ som är tillgängliga. Du kan t.ex. bara markera **[!UICONTROL Hourly]** om du har en eller två dagars tidsram markerad. Du kan bara välja **[!UICONTROL Yearly]** granularitet om du har valt mer än ett år.

Så här anger du rapportgranularitet:

1. Generera en trendrapport, till exempel **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Klicka på **[!UICONTROL View by]** klicka på en granularitet.

## Kör en veckodagsrapport {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Du kan köra rapporter på en viss veckodag, till exempel för varje måndag i ett visst datumintervall.

<!-- 

t_reports_day_of_week.xml

 -->

Den här funktionen gäller endast för trendrapporter som filtrerats med datumintervallet Vecka eller Dag.

Så här kör du en veckodagsrapport:

1. Kör en trendrapport över ett angivet datumintervall.
1. Klicka på **[!UICONTROL Day of Week]** och klicka sedan på en dag.
