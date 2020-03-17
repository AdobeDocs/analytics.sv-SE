---
title: Beräknade mätsummor
description: Läs om hur de beräknade mätvärdena skiljer sig åt i analysverktygen
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Beräknade mätsummor

Hur beräknade måttsummor visas skiljer sig mellan [!DNL Reports & Analytics] och [!DNL Analysis Workspace]. I det här avsnittet förklaras skillnaderna.

## Beräknade mätvärden summor i [!DNL Reports & Analytics]

När du visar rapporter i [!DNL Reports & Analytics]visas beräknade värden alltid `n/a` under summan. Eftersom alla beräknade värden är användardefinierade, finns det många tillfällen då summan inte stämmer. Titta på följande exempel:

Din organisation har skapat det beräknade måttet `orders` / `visits` för att fastställa hur många besök i procent som köpt något på din webbplats. Om du har lagt in detta mätvärde i en produktrapport, kan flera produkter tillskrivas en enda order. Och flera produkter kan tillskrivas ett enda besök. Om en beräknad mätsumma ingick i den här rapporten uppstår följande frågor:

| Fråga | Svar |
|---|---|
| Låter det vettigt att summera radobjekten? | Det gör det inte, eftersom flera produkter kan inkluderas i en enda beställning och flera produkter kan inkluderas vid ett enda besök. Om radobjekten summerades skulle de totala beställningarna och de totala besöken inte matcha de faktiska totala beställningarna och de totala besöken. |
| Låter det vettigt att ta totalorder och totalbesök? | Nej, eftersom summan inte matchar summan för de enskilda radobjekten. Dessutom beräknas totalsumman för beställningar och Totalt antal besök separat. |

Eftersom det inte finns någon logisk och konkret metod för att avgöra om ett beräknat mätresultat är rimligt vid rapportering, utelämnas hela mätvärdet. Om du vill få en totalsumma kan du göra något av följande:

* Skapa ett beräknat mätvärde som innehåller de totala versionerna av mätvärdena som du vill inkludera.
* Skapa en Data Extract-rapport som kan schemaläggas.
* Skapa en databegäran i [!DNL ReportBuilder].
* Använd [!DNL Analysis Workspace] (se nedan).

## Beräknade metriska summor i [!DNL Analysis Workspace]

När du visar data i Analysis Workspace visas i de flesta fall beräknade mätvärden. I vissa fall går det inte att ange en summa, t.ex. när raderna i rapporten har blandat format (t.ex. decimal och valuta).

När summorna visas beräknas de ofta på serversidan, vilket innebär att den totala mängden avduplicerade mått, som besök eller besökare. Under vissa omständigheter genereras beräknade värden på klientsidan genom summering över tabellraderna, vilket innebär att summan inte avduplicerar mått som besök eller besökare. Detta inträffar:

* När [statiska rader](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) används i frihandstabeller markeras **[!UICONTROL Show as sum of current rows]** alternativet (standard).
* I [Donut-visualiseringen](/help/analyze/analysis-workspace/visualizations/donut.md)blir siffrorna 100 %.
