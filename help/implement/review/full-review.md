---
title: Fullständig granskning
description: Se över implementeringen var sjätte månad för att säkerställa fortsatt anpassning till affärsbehoven och nyckeltalen.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
source-git-commit: 4cbc654b6a17a84b373c254a0dd0e44a1740872d
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Fullständig granskning (för granskning av implementeringen två gånger per år)

Varför ska ni granska implementeringen var sjätte månad? Eftersom ni måste se till att implementeringen är anpassad efter era affärsbehov! Ni vill också ta itu med eventuella problem med datakvaliteten, som är små och som innan de växer till stora dataproblem som kan urholka intressenternas förtroende. Utöver dessa fullständiga granskningar var sjätte månad bör du även göra [fokuserade granskningar](/help/implement/review/focused-review.md) efter varje webbplatsrelease.

## 1. Se till att implementeringen fortfarande är helt anpassad efter våra affärsbehov

Träffa företagsägaren och/eller analytikerna för att se hur verksamhetens behov förändras. Ta reda på hur ni uppdaterar nyckeltal och mätplaner för de behov eller mätmöjligheter som för närvarande inte uppfylls av er implementering. Kom ihåg att registrera dina ändringar i din [BRD och SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## 2. Se till att mätvärdena och variablerna fortfarande fungerar bra.

Granska kortfattat alla mätvärden och variabler, i den ordning de är viktiga för företaget, för att säkerställa att data samlas in på rätt sätt. Börja med dina viktigaste mått och variabler - de som är kopplade till dina [5 KPI:er](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html#review). Så här gör du:

* Skapa instrumentpaneler för att se månatliga trendvyer av dina mått och variabler (eller konfigurera [intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html) för var och en av dem) för att säkerställa att du får de data du förväntar dig och att data är korrekta. Om du hittar avvikelser bör du undersöka datalagret, tagghanteringsreglerna och bearbetningsreglerna för att ta reda på varför.
* Kör [Analytics Health Dashboard](https://assets.adobe.com/public/8ff304bb-18e0-434b-54d1-39199422ba1c) igen för att övervaka breda trender för mått och variabler.

Tillåt inte implementeringen att bli fullödig med mätvärden och variabler som du inte behöver. Inaktivera mått eller variabler som företaget inte längre behöver eller använder. Du kanske vill ta bort eller återanvända dem senare.

## 3. Uppdatera dina nyckeltal

Nu när du har en uppdaterad vy över affärsmålen kan du bedöma om du verkligen har valt de 5 *viktigaste* KPI:erna (Key Performance Indicators). Du får bara ha 5! Dessa nyckeltal kan vara mått som intäkter eller beräknade värden som intäkter per besök, och mätvärdena kan också innehålla variabler. Mer information finns i [Definiera de fem viktigaste KPI:erna](/help/implement/review/define-kpis.md).
