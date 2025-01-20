---
title: Vad är Cohort Analysis och hur fungerar den?
description: Gräv djupare in i informationen om er målgrupp och dela in i relaterade grupper med Cohort Analysis. Läs om kohortanalyser i Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Översikt över kohortabellen {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Kohortabell"
>abstract="Skapa en kohortvisualisering för att gruppera användare baserat på slutförandet av en händelse och analysera det pågående engagemanget och bortfallet över tid."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Kohortabell"
>abstract="Gruppera användarna efter att ha slutfört en händelse, analysera sedan deras pågående engagemang och kraschar över tid.<br/><br/>**Parametrar **<br/>**Inkluderingskriterier**: De komponenter som används för att definiera den inledande besökarkohorten.<br/>**Returvillkor**: Komponenterna som används för att avgöra om en besökare har returnerat."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar kohorttabellen i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Se [Kohorttabell](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

En *`cohort`* är en grupp personer som delar gemensamma egenskaper under en angiven period. [!UICONTROL Cohort Analysis] är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av [!UICONTROL Cohort Analysis] finns på webben, till exempel [Kohortanalys 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mått och segment) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med [!UICONTROL Cohort Analysis]:

* Lansera kampanjer som är utformade för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.

[!UICONTROL Cohort Analysis] är tillgängligt för alla Adobe Analytics-kunder med åtkomsträttigheter till [!UICONTROL Analysis Workspace].

Video om Cohort-tabeller i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/25965/?quality=12)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] stöder inte icke-segmenterbara mått (inklusive beräknade värden), icke-heltalsmått (t.ex. Intäkter) eller förekomster.
>
>Endast mätvärden som kan användas i segment kan användas i [!UICONTROL Cohort Analysis], och de kan bara ökas med >1 åt gången.

## Funktioner för kohortanalyser

I följande avsnitt beskrivs kohortanalysfunktioner som gör det möjligt att finjustera kontrollen över kohorterna som du bygger.

Mer information om hur du skapar en kohort och kör en [!UICONTROL Cohort Analysis]-rapport finns i [Konfigurera en kohortanalysrapport](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention]-tabell

En [!UICONTROL Retention]-kohortrapport returnerar besökare: varje datacell visar det råa antalet och procentandelen besökare i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/retention-report.png)

Här är en video om hur du beräknar kvarhållande av rullande text:

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL Churn]-tabell

En [!UICONTROL Churn]-kohort är omvänd till en kvarhållningstabell och visar de besökare som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/churn-report.png)

Här är en video om bortfallsanalys:

>[!VIDEO](https://video.tv.adobe.com/v/25966/?quality=12)

### [!UICONTROL Rolling Calculation]

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency]-tabell

Mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Detta är ett utmärkt verktyg för för-/efteranalys. Kolumnen **[!UICONTROL Included]** finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension]-kohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner som [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för de här dimensionerna.

![](assets/cohort-customizable-cohort-row.png)
