---
keywords: Analysis Workspace
title: Vad är kohortanalys?
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Vad är kohortanalys?

A *`cohort`* är en grupp personer som delar gemensamma egenskaper under en angiven period. Kohortanalys är till exempel användbart när du vill veta hur en kohort interagerar med ett varumärke. Du kan enkelt upptäcka ändringar i trender och sedan svara på dem. (Förklaringar av kohortanalyser finns på webben, t.ex. i [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

När du har skapat en kohortrapport kan du strukturera komponenterna (specifika dimensioner, mått och segment) och sedan dela kohortrapporten med vem som helst. Se [Kuratera och dela](/help/analyze/analysis-workspace/curate-share/curate.md).

Exempel på vad du kan göra med kohortanalys:

* Lansera kampanjer som utformats för att ge önskat resultat.
* Byt marknadsföringsbudget vid exakt rätt tidpunkt i kundlivscykeln.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.
* Visa en kohortanalysrapport i en rapport för guidad analys.
* Identifiera när en testversion eller ett erbjudande ska avslutas för att maximera värdet.
* Få idéer för A/B-testning inom områden som priser, uppgraderingsalternativ osv.

Kohortanalys är tillgängligt för alla Analytics-kunder med åtkomstbehörighet till Analysis Workspace.

[Kohortanalys på YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>Kohortanalys stöder inte beräknade värden.

## Funktioner för kohortanalyser

I januari 2019 lanserade Adobe en ny och avsevärt förbättrad version av Cohort Analysis. Det ger en mycket mer finjusterad kontroll över de kohorter du bygger. Här är de aktuella förbättringarna:

### Bevarandetabell

En rapport om kundlojalitet returnerar besökare: varje datacell visar det obearbetade antalet och den procentuella andelen besökare i kohorten som utförde åtgärden under den tidsperioden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/retention-report.png)

### Churn-tabell

En Churn-kohort är omvänd till ett kvarhållandebord och visar de besökare som inte uppfyller eller aldrig uppfyller returkriterierna för din kohort över tiden. Du kan ta med upp till 3 mätvärden och upp till 10 segment.

![](assets/churn-report.png)

### Rullande beräkning

Gör att du kan beräkna kvarhållning eller kurva baserat på föregående kolumn, inte den inkluderade kolumnen.

![](assets/cohort-rolling-calculation.png)

### Latenstabell

Mäter den tid som har gått före och efter det att inkluderingshändelsen inträffade. Detta är ett utmärkt verktyg för för-/efteranalys. Kolumnen Inkluderat finns i mitten av tabellen och tidsperioder före och efter inkluderingshändelsen visas på båda sidor.

![](assets/cohort-latency.png)

### Anpassad dimensionskohort

Skapa kohorter baserat på en vald dimension, och inte tidsbaserade kohorter, som är standard. Använd dimensioner som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner.

![](assets/cohort-customizable-cohort-row.png)

Instruktioner om hur du konfigurerar och kör en kohortrapport finns i [Konfigurera en kohortanalysrapport](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

