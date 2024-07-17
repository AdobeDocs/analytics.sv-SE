---
description: Hur Workspace-summor beräknas.
title: Workspace summor
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: f4032ac06c9057635dd0526ad046c4640c6350bf
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Workspace summor

I frihandstabeller visas en summeringsrad på varje uppdelningsnivå och kan visa två summor:

* **[!UICONTROL Grand Total]** (antal grå &#39;av&#39;) - det här totala antalet representerar alla träffar som har samlats in, ibland kallat &#39;totalt antal rapportsviter&#39;. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas.
* **[!UICONTROL Table Total]** (svart tal) - den här summan är vanligtvis lika med eller en delmängd av [!UICONTROL Grand Total]. Alla tabellfilter som används i frihandstabellen, inklusive alternativet [!UICONTROL Include None], visas.

![](assets/total-row.png)

## Visa total inställning {#display-total}

Under **[!UICONTROL Column Settings]** finns alternativ för **[!UICONTROL Show Totals]** och **[!UICONTROL Show Grand Total]**. Om de här inställningarna inte är markerade tas summorna bort från tabellen. Detta kan vara önskvärt om summorna inte är rimliga, t.ex. i vissa [beräknade mätscenarier](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html).

![](assets/column-settings-total.png)

## Inställningar för totalt antal statiska rader {#static-row-total}

[Statiska radsummor ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.html) fungerar på olika sätt och styrs under **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - Detta visar en summa på klientsidan av raderna i tabellen, vilket innebär att summan **inte** tar bort dubbletter som besök eller besökare.
* **[!UICONTROL Show Grand Total]** - det här visar en serversidessumma, vilket innebär att summan kommer att ta bort dubbletter som besök eller besökare.

![](assets/static-rows.png)

## Frågor och svar

| Frågor | Svar |
|---|---|
| Vilken summa är procentsatserna för gråa kolumner baserade på? | Detta beror på inställningen **[!UICONTROL Percentages]** under **[!UICONTROL Row Settings]**:<ul><li>Beräkna procentandelar per kolumn - Det här är standardinställningen. Procentsatserna baseras på tabellsumman.</li><li>Beräkna procentandelar per rad - Procentsatserna baseras på totalsumman.</li></ul> |
| Hur påverkar inställningen för **[!UICONTROL Include Unspecified (None)]** summorna? | Om inställningen **[!UICONTROL Include Unspecified (None)]** inte är markerad tas raden Ingen/Ospecificerad bort från tabellen, Tabellsumma, och utförs på alla beräknade mått som använder måtten [&#39;Total&#39; ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| När anpassade tabellfilter tillämpas på en frihandstabell, gör jag då alla mina beräknade värden och villkorsstyrda formateringskonton för filtret? | Inte just nu. **[!UICONTROL Include Unspecified (None)]** räknas med, men anpassade tabellfilter påverkar inte följande:<ul><li>Kolumnens max/min-intervall som villkorsstyrd formatering använder ser ut över alla data.</li><li>Beräknade mätvärden som utnyttjar **[!UICONTROL Grand Total]** mätningstyper.</li><li>Beräknade mätvärden med funktioner som beräknas över rader i en friformstabell, t.ex. kolumnsumma, kolumnmax, kolumnmin, antal, medel, medel, medel, percentil, kvartil, radantal, standardavvikelse, varians, ackumulerat, kumulativt genomsnitt, regressionsvarianter, T-poäng, T-test, Z-poäng, Z-test, Z-test.</li></ul> |
| I beräknade värden, vad återspeglar den **[!UICONTROL Grand Total]**-metriska typen? | **[!UICONTROL Grand Total]** fortsätter att referera till **[!UICONTROL Grand Total]** och reflekterar inte filter som används i en tabell eller **[!UICONTROL Table Total]**. |
| Vilken summa visas när data kopieras och klistras in från en frihandstabell eller hämtas via CSV? | Den totala raden återspeglar endast **[!UICONTROL Table Total]** och respekterar inställningen för kolumnen **[!UICONTROL Show Totals]**. |
