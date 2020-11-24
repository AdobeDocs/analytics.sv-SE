---
title: Genomförandegranskning (var sjätte månad)
description: Se över implementeringen var sjätte månad för att säkerställa fortsatt anpassning till affärsbehoven och nyckeltalen.
translation-type: tm+mt
source-git-commit: 145b31d01b7ec52ae3c65035774a5be54abbc51a
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Genomförandegranskning (var sjätte månad)

Varför ska ni granska implementeringen var sjätte månad? Eftersom ni måste se till att implementeringen är anpassad efter era affärsbehov! Ni vill också ta itu med eventuella problem med datakvaliteten, samtidigt som de är små och innan de växer till större dataproblem som kan urholka intressenternas förtroende. Förutom dessa stora recensioner bör du också göra [mindre granskningar](/help/implement/review/minor-review.md) varje gång du får en stor webbplatsrelease.

## 1. Är min implementering fortfarande helt anpassad efter våra affärsbehov?

Träffa företagsägaren och/eller analytikerna för att se hur verksamhetens behov förändras. Ta reda på hur ni uppdaterar nyckeltal och mätplaner för de behov eller mätmöjligheter som för närvarande inte uppfylls av er implementering. Kom ihåg att registrera dina ändringar i din BRD och SDR.

## 2. Hur är datakvaliteten för mina mätvärden och variabler?

Granska kortfattat alla mätvärden och variabler, i den ordning de är viktiga för företaget, för att säkerställa att data samlas in korrekt.

* Skapa instrumentpaneler för att se månatliga trendvyer av mätvärden och variabler (eller konfigurera intelligenta aviseringar för var och en av dem) för att säkerställa att ni får de data ni förväntar er och att data är korrekta.
Om du hittar avvikelser bör du undersöka datalagret, tagghanteringsreglerna och bearbetningsreglerna för att ta reda på varför.
* Kör Analytics Health Dashboard igen för att övervaka breda trender för mätvärden och variabler.
Tillåt inte implementeringen att bli fullödig med mätvärden och variabler som du inte behöver. Inaktivera mått eller variabler som företaget inte längre behöver eller använder. Du kanske vill ta bort eller återanvända dem senare.

## 3. Har mina nyckeltal förändrats?

Nu när du har en uppdaterad bild av affärsmålen kan du bedöma om du verkligen har valt de 5 viktigaste KPI:erna (Key Performance Indicators). Du får bara ha 5! Dessa nyckeltal kan vara mått som intäkter eller beräknade värden som intäkter per besök, och mätvärdena kan också innehålla variabler. Mer information finns i [Definiera de fem viktigaste KPI:erna](/help/implement/review/define-kpis.md) .
