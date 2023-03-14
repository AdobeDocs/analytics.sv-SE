---
description: Hur summor för arbetsytan beräknas.
title: Summor för arbetsyta
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Summor för arbetsyta

I frihandstabeller visas en summeringsrad på varje uppdelningsnivå och kan visa två summor:

* **[!UICONTROL Grand Total]** (grå &#39;av&#39;-tal) - denna summa representerar alla träffar som har samlats in, ibland kallat &#39;rapportsvitens totala&#39;. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas.
* **[!UICONTROL Table Total]** (svart tal) - den här summan är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Alla tabellfilter som används i frihandstabellen, inklusive [!UICONTROL Include None] alternativ.

![](assets/total-row.png)

## Visa total inställning {#display-total}

Under **[!UICONTROL Column Settings]** finns det alternativ för **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]**. Om de här inställningarna inte är markerade tas summorna bort från tabellen. Detta kan vara önskvärt om summorna inte stämmer, t.ex. i vissa [Beräknade måttscenarier](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Inställningar för totalt antal statiska rader {#static-row-total}

[Statisk rad](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.html) summan beter sig på olika sätt och styrs under **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - här visas en summa av raderna på klientsidan, vilket innebär att summan **not** avduplicera mätvärden som besök eller besökare.
* **[!UICONTROL Show Grand Total]** - detta visar en summa på serversidan, vilket innebär att summan kommer att ta bort dubbletter av statistik som besök eller besökare.

![](assets/static-rows.png)

## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilken summa är procentsatserna för gråa kolumner baserade på? | Det beror på **[!UICONTROL Percentages]** ange markering under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Det här är standardinställningen. Procentsatserna baseras på tabellsumman.</li><li>Beräkna procentandelar per rad - Procentsatserna baseras på totalsumman.</li></ul> |
| Hur fungerar **[!UICONTROL Include Unspecified (None)]** Vill du ställa in effektsummor? | Om **[!UICONTROL Include Unspecified (None)]** inställningen är avmarkerad, raden Inget/Ospecificerad tas bort från tabellen, tabellen Totalt och utförs på alla beräknade mätvärden som använder [Måtttyperna &#39;Total&#39;](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| När anpassade tabellfilter tillämpas på en frihandstabell, gör jag då alla mina beräknade värden och villkorsstyrda formateringskonton för filtret? | Inte just nu. **[!UICONTROL Include Unspecified (None)]** tas med i beräkningen, men anpassade tabellfilter påverkar inte följande:<ul><li>Kolumnens max/min-intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mätvärden som ger **[!UICONTROL Grand Total]** mätningstyper.</li><li>Beräknade mätvärden med funktioner som beräknas över rader i en friformstabell, t.ex. kolumnsumma, kolumnmax, kolumnmin, antal, medel, medel, medel, percentil, kvartil, radantal, standardavvikelse, varians, ackumulerat, kumulativt genomsnitt, regressionsvarianter, T-poäng, T-test, Z-poäng, Z-test, Z-test.</li></ul> |
| Vad gör **[!UICONTROL Grand Total]** Vill du spegla metrisk typ? | **[!UICONTROL Grand Total]** fortsätter att referera till **[!UICONTROL Grand Total]** och återspeglar inte filter som används i en tabell eller **[!UICONTROL Table Total]**. |
| Vilken summa visas när data kopieras och klistras in från en frihandstabell eller hämtas via CSV? | Summaraden återspeglar **[!UICONTROL Table Total]** endast och respekterar kolumnen **[!UICONTROL Show Totals]** inställning. |
