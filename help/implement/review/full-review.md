---
title: Fullständig granskning
description: Se över implementeringen var sjätte månad för att säkerställa fortsatt anpassning till affärsbehoven och nyckeltalen.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Fullständig granskning (för granskning av implementeringen två gånger per år)

Varför ska ni granska implementeringen var sjätte månad? Eftersom ni måste se till att implementeringen är anpassad efter era affärsbehov! Ni vill också ta itu med eventuella problem med datakvaliteten, som är små och som innan de växer till stora dataproblem som kan urholka intressenternas förtroende. Förutom dessa fullständiga granskningar var sjätte månad bör du också göra [Fokuserade granskningar](/help/implement/review/focused-review.md), efter varje webbplatsrelease.

## 1. Se till att implementeringen fortfarande är helt anpassad efter våra affärsbehov

Träffa företagsägaren och/eller analytikerna för att se hur verksamhetens behov förändras. Ta reda på hur ni uppdaterar nyckeltal och mätplaner för de behov eller mätmöjligheter som för närvarande inte uppfylls av er implementering. Kom ihåg att registrera dina ändringar i [BRD och SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## 2. Se till att mätvärdena och variablerna fortfarande fungerar bra.

Granska kortfattat alla mätvärden och variabler, i den ordning de är viktiga för företaget, för att säkerställa att data samlas in på rätt sätt. Börja med era viktigaste mätvärden och variabler - de som är kopplade till er [de 5 främsta KPI:erna](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html#review). Så här gör du:

* Skapa instrumentpaneler för att se månatliga trender över mätvärden och variabler (eller konfigurera [intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html) för var och en av dem) för att säkerställa att ni får de data ni förväntar er och att data är korrekta. Om du hittar avvikelser bör du undersöka datalagret, tagghanteringsreglerna och bearbetningsreglerna för att ta reda på varför.
* Kör om [Kontrollpanel för analyshälsa](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) för att övervaka breda trender för mätvärden och variabler.

Tillåt inte implementeringen att bli fullödig med mätvärden och variabler som du inte behöver. Inaktivera mått eller variabler som företaget inte längre behöver eller använder. Du kanske vill ta bort eller återanvända dem senare.

## 3. Uppdatera dina nyckeltal

Nu när du har en uppdaterad bild av affärsmålen kan du se om du verkligen har valt de 5 *mest* viktiga nyckeltal (KPI). Du får bara ha 5! Dessa nyckeltal kan vara mått som intäkter eller beräknade värden som intäkter per besök, och mätvärdena kan också innehålla variabler. Se [Definiera de fem viktigaste KPI:erna](/help/implement/review/define-kpis.md) för mer information.
