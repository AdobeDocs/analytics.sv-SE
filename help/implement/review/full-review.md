---
title: Fullständig granskning
description: Se över implementeringen var sjätte månad för att säkerställa fortsatt anpassning till affärsbehoven och nyckeltalen.
translation-type: tm+mt
source-git-commit: ad7274dbed3b85ca24cd92bf3a0d36d1f2e3597b
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Fullständig granskning (för granskning av implementeringen två gånger per år)

Varför ska ni granska implementeringen var sjätte månad? Eftersom ni måste se till att implementeringen är anpassad efter era affärsbehov! Ni vill också ta itu med eventuella problem med datakvaliteten, samtidigt som de är små och innan de växer till större dataproblem som kan urholka intressenternas förtroende. Förutom dessa fullständiga granskningar var sjätte månad bör du även göra [fokuserade granskningar](/help/implement/review/focused-review.md) efter varje webbplatsrelease.

## 1. Se till att implementeringen fortfarande är helt anpassad efter våra affärsbehov.

Träffa företagsägaren och/eller analytikerna för att se hur verksamhetens behov förändras. Ta reda på hur ni uppdaterar nyckeltal och mätplaner för de behov eller mätmöjligheter som för närvarande inte uppfylls av er implementering. Kom ihåg att registrera dina ändringar i [BRD och SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 2. Se till att mätvärden och variabler fortfarande fungerar bra.

Granska kortfattat alla mätvärden och variabler, i den ordning de är viktiga för företaget, för att säkerställa att data samlas in korrekt. Börja med dina viktigaste mått och variabler - de som är kopplade till dina [5 KPI:er](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html?lang=en#review). Så här gör du:

* Skapa instrumentpaneler för att se månatliga trendvyer av mätvärden och variabler (eller konfigurera [intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) för var och en av dem) för att vara säker på att du får de data du förväntar dig och att data är korrekta. Om du hittar avvikelser bör du undersöka datalagret, tagghanteringsreglerna och bearbetningsreglerna för att ta reda på varför.
* Kör om [Analytics Health Dashboard](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) för att övervaka breda trender för mätvärden och variabler.

Tillåt inte implementeringen att bli fullödig med mätvärden och variabler som du inte behöver. Inaktivera mått eller variabler som företaget inte längre behöver eller använder. Du kanske vill ta bort eller återanvända dem senare.

## 3. Uppdatera dina KPI:er.

Nu när du har en uppdaterad vy över affärsmålen kan du bedöma om du verkligen har valt de 5 *viktigaste* viktiga KPI:erna (Key Performance Indicators). Du får bara ha 5! Dessa nyckeltal kan vara mått som intäkter eller beräknade värden som intäkter per besök, och mätvärdena kan också innehålla variabler. Mer information finns i [Definiera de fem viktigaste KPI:erna](/help/implement/review/define-kpis.md).