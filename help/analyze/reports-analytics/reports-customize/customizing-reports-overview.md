---
description: När du har kört en rapport kan du anpassa rapporten för att visa och analysera data efter dina behov. Du kan filtrera rapportdata, ändra hur data presenteras grafiskt, ändra granularitet för datum och så vidare.
title: Anpassa rapporter – översikt
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Rapporter och analysgrunder
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 3%

---

# Anpassa rapporter – översikt

När du har kört en rapport kan du anpassa rapporten för att visa och analysera data efter dina behov. Du kan filtrera rapportdata, ändra hur data presenteras grafiskt, ändra granularitet för datum och så vidare.

## Skapa en anpassad rapport {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Steg som beskriver hur du sparar en rapports aktuella konfiguration som en ny anpassad rapport som alla användare kan se.

<!-- 

t_reports_custom.xml

 -->

Endast administratörer kan skapa en anpassad rapport. När du skapar en anpassad rapport läggs den till på huvudrapporteringsmenyn bredvid den rapport som den baseras på.

**Skapa en anpassad rapport**

1. Kör en rapport och konfigurera den efter behov.
1. Klicka på **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Namnge rapporten och klicka sedan på **[!UICONTROL Save.]**

   Se till att du inte duplicerar ett befintligt rapportnamn.

>[!MORELIKETHIS]
>
>* [Menyanpassning](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/customize-menus.html)


## Välj ett datum eller datumintervall {#task_9BEF7D4D839A4748B76E8500D1406C34}

Steg som beskriver hur varmt det är att använda väljer du tidsperioder för rapportdata.

<!-- 

t_reports_select_date.xml

 -->

Du kan välja specifika dagar, veckor, månader eller år. Du kan också köra jämförelserapporter.

När du öppnar en kontrollpanel med rapporter som har olika datumintervall kan du välja ett nytt datumintervall i kalendern. Ändringarna gäller för alla rapporter på kontrollpanelen.

**Välj ett datumintervall**

1. Kör en rapport.
1. Klicka på kalenderikonen högst upp till höger.
1. Välj ett datum.

   Ni kan:

   * Visa dagar, månader eller årsperioder (upp till tre).
   * Dra markören över datum för att markera ett intervall.
   * Ange datum manuellt.
   * Klicka på ett månadsnamn för att välja en månad.
   * Klicka på **[!UICONTROL Select Preset]** för att välja ett förinställt datum.
   * Jämför datum.

1. Klicka på **[!UICONTROL Run Report]**.

## Jämför datum {#task_95155C3700774B709F5FB81AE96B0824}

Steg som beskriver hur du kan använda kalendern för att köra datumjämförelser mellan rankade rapporter.

<!-- 

t_reports_comparing_dates.xml

 -->

Du kan inte jämföra datum mellan trendrapporter.

>[!NOTE]
>
>Om du vill utföra en datumjämförelse på nyckelvärden i en kontrollpanel kan du hämta data till [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) med två separata förfrågningar. Du kan sedan använda egna formler i Excel för att analysera skillnaden mellan de två formlerna.

Så här jämför du datum mellan rankade rapporter i Rapporter och analyser:

1. Kör en rapport.
1. Klicka på kalendern längst upp till höger.
1. Klicka på **[!UICONTROL Compare Dates]**.
1. Markera de datum som du vill använda.
1. Klicka på **[!UICONTROL Run Report]**.

## Visa ett procentvärde som ett diagram {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Steg som beskriver hur du anger om procentandelen i en rapporttabell ska visas som ett diagram.

<!-- 

t_reports_graph_percent.xml

 -->

Den här visualiseringen är även tillgänglig i rapportlets på kontrollpanelen.

1. Kör en rapport som har stöd för procentsatser, t.ex. en [!UICONTROL Pages Report].
1. Klicka på **[!UICONTROL Percent Shown As: Graph]**.

## Normalisera rapportdata {#task_8005B55E59BD479DA67BC618FF8BC94A}

Steg som beskriver hur rapportdata normaliseras.

<!-- 

t_reports_normalize.xml

 -->

När du har kört en rapport med jämförda datum, eller för A/B-jämförelser, kan du normalisera data för att visa procentandelen av förändring mellan rapporterna. Den sekundära datauppsättningen justeras för att kompensera för skillnader i antalet valda dagar eller för olika trafikvolymer.

**Så här normaliserar du rapportdata**

1. Kör en rapport som stöder datumjämförelser.
1. Klicka på **[!UICONTROL Compare Dates]** och ange sedan din datumjämförelse.
1. Klicka på **[!UICONTROL Run Report]**.
1. Klicka på **[!UICONTROL Normalize Data: Yes]**.

## Välj en sida för en rapport {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Steg som beskriver hur du väljer en viss sida på sidorna på webbplatsen för en rapport.

<!-- 

t_reports_select_page.xml

 -->

1. Generera en rapport, till exempel en [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Klicka på länken **[!UICONTROL Selected Page]**.
1. Markera de sidor som du vill visa på [!UICONTROL Choose Page].
1. Leta reda på sidan.
1. Klicka på **[!UICONTROL OK.]**

## Jämför rapportsviter {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Steg som beskriver hur du visar rapporter från två rapportsviter i samma rapport.

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
* Målgrupp
* Undersökning

**Jämför rapportsviter**

1. Generera en rapport som gör att du kan jämföra rapporter.
1. Klicka på länken **[!UICONTROL Compare to Site]**.
1. Leta reda på rapportsviten.
1. Klicka på **[!UICONTROL OK.]**

## Ange rapportgranularitet {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Steg som beskriver hur rapportsummorna ska visas per timme, dag, varje vecka, varje månad, varje kvartal eller varje år.

<!-- 

t_reports_granularity.xml

 -->

Rapportens tidsperiod avgör vilka granularitetsalternativ som är tillgängliga. Du kan till exempel bara välja **[!UICONTROL Hourly]** om du har en eller två dagars tidsram markerad. Du kan bara välja granularitet **[!UICONTROL Yearly]** om du har valt mer än ett år.

**Ange rapportgranularitet**

1. Generera en trendrapport, till exempel **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Klicka på länken **[!UICONTROL View by]** och klicka sedan på en granularitet.

## Kör en veckodagsrapport {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Steg som beskriver hur rapporter ska köras på en viss veckodag, till exempel för varje måndag i ett visst datumintervall.

<!-- 

t_reports_day_of_week.xml

 -->

Den här funktionen gäller endast för trendrapporter som filtrerats med datumintervallet Vecka eller Dag.

1. Kör en trendrapport över ett angivet datumintervall.
1. Klicka på länken **[!UICONTROL Day of Week]** och klicka sedan på en dag.

## Knappen Prova i arbetsyta {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Om du klickar på **[!UICONTROL Try In Workspace]** längst upp i en rapport läses samma rapport in i Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

De flesta rapporter i Rapporter och analyser innehåller nu knappen Testa i arbetsytan så att du kan återskapa den aktuella vyn i Analysis Workspace för ytterligare anpassning.

För närvarande är knappen bara tillgänglig om ditt användarnamn har fullständig behörighet till Analysis Workspace.

Mer information om alla sätt att anpassa rapporten finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html)-guiden.
