---
description: Visar information om i vilken ordning sidorna på webbplatsen nås. Du kan samla in information om var en besökare besöker webbplatsen före och efter en sida.
title: Sökvägsrapporter
topic: Ad hoc analysis
uuid: 5881cb1c-6d66-49fe-ac84-70b82662acd2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sökvägsrapporter

Visar information om i vilken ordning sidorna på webbplatsen nås. Du kan samla in information om var en besökare besöker webbplatsen före och efter en sida.

## Sökvägsrapporter {#concept_CB32E270FB9E4D929C91FDFE428CB224}

Visar information om i vilken ordning sidorna på webbplatsen nås. Du kan samla in information om var en besökare besöker webbplatsen före och efter en sida.

Sökvägsrapporter innehåller detaljerade standardanalysrapporter och valfria avancerade analysrapporter som visar klickströmmen av visade sidor. Du kan identifiera fullständiga banor, längsta banor och de vanligaste banorna. förklara sidflöde, bortfall och utfall grafiskt, visa nya och föränderliga mönster över tid, och analysera ingångs- och avslutsbanor.

**[!UICONTROL Next Page Flow]** eller **[!UICONTROL Next Site Flow]**: Visar en förgreningsbild på två nivåer av en markerad sida (eller avsnitt, avdelning och så vidare) som besökarna ser efter att ha flyttat bort från den markerade sidan. Använd den här rapporten för att analysera och identifiera de steg besökarna tar oftast efter att ha visat en vald sida. Du kan:

* Förstå vilka steg som utförs oftast när du har visat en markerad sida.
* Optimera sajtens sökvägsdesign för att flytta trafiken till önskad målsida.
* Identifiera vart besökarna ska åka istället för de önskade målsidorna.

**[!UICONTROL Next Page]** (eller nästa kategori): Innehåller detaljerad analys av webbplatsens sökväg genom att visa de sidor på webbplatsen som besökarna har visat efter att ha sett en vald sida. När du till exempel väljer och rapporterar en webbplats visar rapporten de tio viktigaste landningssidorna, med de fem populäraste nästa sidorna som listas under varje landningssida. Dessa data kan hjälpa er att förstå vilket innehåll, vilka funktioner och vilka andra data som oftast tvingar era besökare att gå igenom er webbplats.

**[!UICONTROL Previous Page Flow]** (eller andra föregående kategoriflöden): Visar två nivåer av de mest populära sidorna som besökarna ser före den valda sidan. Rapporten visar också när besökare kommer in på er webbplats.

**[!UICONTROL Previous Page]** (eller andra tidigare kategorier): Innehåller detaljerad analys av webbplatsens sökväg genom att visa de sidor på webbplatsen som besökarna visade innan de såg en vald sida på webbplatsen.

**[!UICONTROL Fallout]**: Visar besöksattribuering och konverteringsgrader mellan de kontrollpunkter du anger. Stegen ordnas uppifrån och ned, med råa siffror och procentsatser till vänster och konverterings- och nedfallsprocenten till höger.

Mer information finns i [Utfallsrapport](/help/analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347) .

**[!UICONTROL Path Length]**: Visar hur djupa besökare surfar in på din webbplats (både i procent och totalt antal). Rapporten visar med andra ord hur många sidor den genomsnittliga besökaren på webbplatsen har innan han/hon lämnar den.

**[!UICONTROL Page Analysis]**: Innehåller en delmängd av rapporter där du kan analysera följande:

* **[!UICONTROL Page Summary / Site Category Summary]**: Ger dig allt du behöver veta om sidrapporten. Den samlar in och organiserar sidspecifik information om en sida och presenterar den i en enda rapport.
* **[!UICONTROL Reloads]**: Visar hur många gånger besökare har läst in enskilda sidor.
* **[!UICONTROL Time Spent on Page / Site Category]**: Visar hur lång tid besökarna kan bläddra bland enskilda sidor på webbplatsen. Tidsåtgången är uppdelad i tio kategorier: mindre än 15 sekunder, 15-30 sekunder, 30-60 sekunder, 1-3 minuter, 3-5 minuter, 5-10 minuter, 10-15 minuter, 15-20 minuter, 20-30 minuter och mer än 30 minuter.
* **[!UICONTROL Clicks to Page]**: Identifierar antalet klick besökare använde för att komma åt varje sida på din webbplats. Djupet för en sida mäts genom att antalet sidor som visas före sidan räknas.

**[!UICONTROL Entries & Exits]**: Rapporten visar [!UICONTROL Entry Page] hur många procent och hur många besök du har gjort, vilka sidor på din webbplats som är de första besökarna ser. Du kan visa:

* **[!UICONTROL Entry Pages]** (eller avsnitt): Visar, i procent och totalt, vilka sidor på webbplatsen som är de första sidorna som en ny besökare ser. Du kan använda den här rapporten för att identifiera vilka av dina webbsidor som är de vanligaste ingångspunkterna, optimera de primära startpunkterna på din webbplats och dirigera trafik till dina huvudmeddelanden.
* **[!UICONTROL Original Entry Pages]**: Visar den första sidan som visas för förstagångsbesökare på webbplatsen. Varje användare räknas bara en gång om de inte tar bort sina cookies eller spåras inte med cookies.
* **[!UICONTROL Single Page Visits]**: Visar sidor som oftast både är in- och avslutssidor för besökarsessioner.
* **[!UICONTROL Exit Pages]**: Visar de sidor på webbplatsen som var de sista sidor som besökarna visade innan de lämnade webbplatsen, i procent och vid det totala antalet besök.

## Utfallsrapport {#concept_0ED452F3B1D04A19A59DD04D76D20347}

Här [!UICONTROL Fallout Report] visas var besökarna lämnar (fallout) och fortsätter igenom (fallthrough) en fördefinierad sidsekvens. Här visas konverterings- och utfallsfrekvenser mellan varje steg. Du kan till exempel spåra en besökares utfallspunkter under en köpprocess. Du väljer en startpunkt och en slutpunkt och lägger till mellanliggande punkter för att skapa en webbplatsnavigeringsbana.

<!-- 

c_reports_fallout.xml

 -->

Du kan analysera utfallsdata på besöks- eller besöksnivå. Du kan också se en bana som du ser som en graf över utfallet under en viss period. Du kan ange enstaka sidor eller grupper av sidor som rapportkontrollpunkter, eller lägga till mått eller mätvärden i valfri kombination eller sekvens. Du kan också använda kategorier som du konfigurerar i marknadsföringsrapporter och analyser som kontrollpunkter i den här rapporten.

Den här rapporten är användbar för att analysera:

* Konverteringsgrader genom specifika processer på er webbplats (t.ex. ett inköp eller en registreringsprocess).
* Allmänna, bredare trafikflöden: Av de personer som såg hemsidan visar det här flödet hur många som har gjort en sökning och sedan hur många som till slut gick vidare för att titta på ett visst objekt.
* Korrelationer mellan händelser på din webbplats. Korrelationer visar hur många procent av dem som tittade på din integritetspolicy fortsatte att köpa en produkt.

## Kör en utfallsrapport {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

Steg för att köra en [!UICONTROL Fallout Report].

<!-- 

t_fallout.xml

 -->

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL New Report]** > **[!UICONTROL Fallout.]**

   Andra utfallsrapporter finns i **[!UICONTROL Reports]** > **[!UICONTROL Paths]**.

1. (Valfritt) Dra ett segment till [!UICONTROL Drop Segment Here] fältet om du vill filtrera data efter ett visst segment.
1. Dra ett dimensionsobjekt till [!UICONTROL Drop Event or Dimension Items Here] fältet.
1. Klicka på **[!UICONTROL Show Fallout At]**Besök- eller besöksnivå, beroende på om du vill visa bortfallet på besöksnivå eller mellan besökarsessioner.
1. Lägg till dimensionsobjekt, till exempel sidor, i rapporten.

## Tilldela sidor till en utfallsrapport {#task_B386289703494FA7B5A40FF9F97CB537}

Steg för att tilldela sidor till en utfallsrapport.

<!-- 

t_fallout_assign_pages.xml

 -->

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Pages Fallout]**.
1. Leta reda på de sidor som ska läggas till i [!UICONTROL Dimensions] rutan och dra dem sedan till [!UICONTROL Drop Event or Dimension Here] fältet.

## Utfallsrapport - fältbeskrivningar {#reference_74255CC8D6134F349FEBFEC72934C866}

Fältbeskrivningar för [!UICONTROL Fallout] rapporten.

<!-- 

r_dsc_fallout.xml

 -->

| Fält | Beskrivning |
|--- |--- |
| Visa utrullning på besöks- eller besöksnivå | Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå, oavsett besök. Webbplatsanalys-, flödes- och bortfallsrapporter är aktiverade för besökspassning. Om du ändrar den här inställningen returneras rapporten, vilket begränsar data till markeringen. |
| Totalt antal lyckade | En total indikator på om åtgärden lyckades. Detta värde återspeglar värdet i banans sista kontrollpunkt. |
| Totalt genomförda % | Sammanlagt antal besökare vid varje kontrollpunkt. |
| Kontrollpunkt % | Procent av lyckad åtgärd mellan kontrollpunkter. (Inte kumulativ.) |
| Inkludera alla besök | Lägger till alla besök som inledande kontrollpunkt. |
| Utfall | Gör att du kan se sidorna som visas efter att besökaren föll utanför den angivna kontrollpunktssökvägen. |
| Fallthrough | Här kan du se sidorna som visas i nästa steg i den angivna kontrollpunktssökvägen. |
