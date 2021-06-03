---
title: Vad är Cohort Analysis och hur fungerar den?
description: Gräv djupare in i informationen om er målgrupp och dela in i relaterade grupper med Cohort Analysis. Läs om kohortanalyser i Analysis Workspace.
feature: Visualiseringar
role: Business Practitioner, Administrator
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Läs om [!UICONTROL Cohort Analysis] i Adobe Analytics

En *`cohort`* är en grupp personer som delar gemensamma egenskaper under en angiven period. [!UICONTROL Cohort Analysis] är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av [!UICONTROL Cohort Analysis] finns på webben, t.ex. [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mått och segment) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med [!UICONTROL Cohort Analysis]:

* Lansera kampanjer som utformats för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.
* Visa en [!UICONTROL Cohort Analysis]-rapport i en rapport för guidad analys.

[!UICONTROL Cohort Analysis] är tillgängligt för alla Adobe Analytics-kunder med åtkomsträttigheter till  [!UICONTROL Analysis Workspace].

[Självstudievideo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html)  om kohortanalys (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis]
>
>stöder inte icke-segmenterbara mått (inklusive beräknade värden), icke-heltalsvärden (t.ex. Intäkter) eller förekomster. Endast mätvärden som kan användas i segment kan användas i
>[!UICONTROL Cohort Analysis]och de kan bara ökas med 1 i taget.

## Funktioner för kohortanalyser

Följande funktioner gör att du kan finjustera kontrollen över de kohorter du bygger:

### [!UICONTROL Retention] Tabell

En [!UICONTROL Retention]-kohortrapport returnerar besökare: varje datacell visar det obearbetade antalet och den procentuella andelen besökare i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/retention-report.png)

### [!UICONTROL Churn] Tabell

En [!UICONTROL Churn]-kohort är omvänd till en kvarhållningstabell och visar de besökare som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/churn-report.png)

### [!UICONTROL Rolling Calculation]

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Tabell

Mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Detta är ett utmärkt verktyg för för-/efteranalys. Kolumnen **[!UICONTROL Included]** finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Kohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner som [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] eller någon annan dimension i Adobe Analytics för att visa hur kvarhållningen ändras baserat på de olika värdena för de här dimensionerna.

![](assets/cohort-customizable-cohort-row.png)

Instruktioner om hur du konfigurerar och kör en kohortrapport finns i [Konfigurera en kohortanalysrapport](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
