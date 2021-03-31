---
description: Hur summor för arbetsytan beräknas.
title: Summor för arbetsyta
feature: Frihandstabeller
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# Summor för arbetsyta

I frihandstabeller visas en summeringsrad på varje uppdelningsnivå och kan visa två summor:

* **[!UICONTROL Grand Total]** (grå &#39;av&#39;-tal) - denna summa representerar alla träffar som har samlats in, ibland kallat &#39;rapportsvitens totala&#39;. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas.
* **[!UICONTROL Table Total]** (svart tal) - den här summan är vanligtvis lika med eller en delmängd av  [!UICONTROL Grand Total]. Alla tabellfilter som används i friformstabellen, inklusive alternativet [!UICONTROL Include None], visas.

![](assets/total-row.png)

## Visa total inställning {#display-total}

Under **[!UICONTROL Column Settings]** finns det alternativ för **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]**. Om de här inställningarna inte är markerade tas summorna bort från tabellen. Detta kan vara önskvärt om summorna inte är rimliga, t.ex. i vissa [beräknade måttscenarier](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Inställningar för totalt antal statiska rader {#static-row-total}

[Statiska ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.html) radsummor fungerar annorlunda och styrs under  **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - här visas en summering av raderna i tabellen på klientsidan, vilket innebär att summan inte kommer att  **** dubblera mätvärden som besök eller besökare.
* **[!UICONTROL Show Grand Total]** - detta visar en summa på serversidan, vilket innebär att summan kommer att ta bort dubbletter av statistik som besök eller besökare.

![](assets/static-rows.png)

## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilken summa är procentsatserna för gråa kolumner baserade på? | Detta beror på **[!UICONTROL Percentages]**-inställningsvalet under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Det här är standardinställningen. Procentsatserna baseras på tabellsumman.</li><li>Beräkna procentandelar per rad - Procentsatserna baseras på totalsumman.</li></ul> |
| Hur påverkar inställningen **[!UICONTROL Include Unspecified (None)]** summorna? | Om inställningen **[!UICONTROL Include Unspecified (None)]** inte är markerad tas raden Inget/Ospecificerad bort från tabellen, Tabellsumma, och utförs på alla beräknade mått som använder [&#39;Total&#39; metric-typer](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| När anpassade tabellfilter tillämpas på en frihandstabell, gör jag då alla mina beräknade värden och villkorsstyrda formateringskonton för filtret? | Inte just nu. **[!UICONTROL Include Unspecified (None)]** tas med i beräkningen, men anpassade tabellfilter påverkar inte följande:<ul><li>Kolumnens max/min-intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mätvärden som utnyttjar **[!UICONTROL Grand Total]** mätningstyper.</li><li>Beräknade mätvärden med funktioner som beräknas över rader i en friformstabell, t.ex. kolumnsumma, kolumnmax, kolumnmin, antal, medel, medel, medel, percentil, kvartil, radantal, standardavvikelse, varians, ackumulerat, kumulativt genomsnitt, regressionsvarianter, T-poäng, T-test, Z-poäng, Z-test, Z-test.</li></ul> |
| I Beräknade mått, vad återspeglar måtttypen **[!UICONTROL Grand Total]**? | **[!UICONTROL Grand Total]** fortsätter att referera till  **[!UICONTROL Grand Total]** och reflekterar inte filter som används i en tabell eller i  **[!UICONTROL Table Total]**. |
| Vilken summa visas när data kopieras och klistras in från en frihandstabell eller hämtas via CSV? | Den totala raden återspeglar endast **[!UICONTROL Table Total]** och respekterar inställningen för kolumnen **[!UICONTROL Show Totals]**. |

