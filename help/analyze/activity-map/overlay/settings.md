---
description: På inställningspanelen Activity Map kan du ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar.
title: Konfigurera inställningar för Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: ba10ceb73d953ff495613d02dd1ff825b6e518df
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Konfigurera inställningar för Activity Map

På inställningspanelen Activity Map kan du ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar.

Gå till inställningspanelen Activity Map genom att klicka på kugghjulsikonen i verktygsfältet Activity Map.

## Allmänna inställningar {#section_697A12F099494D699A4BF498598178C5}

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Companies]** | Välj tillämpligt inloggningsföretag. |
| **[!UICONTROL Report Suite]** | Listan med rapportsviter som är tillgängliga för dig är inte längre begränsad till de rapportsviter som definieras i webbsidestaggen. Nu kan du ersätta den valda rapportsviten (som motsvarar en av taggarna på sidan) med en annan rapportserie. Den här nya rapportsviten behöver inte länkas till en tagg på sidan. Om du ändrar den markerade rapportsviten i Activity Map Settings kommer alla berörda analysrapporter att uppdateras vid Spara-processen.<br>**Viktigt**: [!UICONTROL Virtual report suites] är inte kompatibelt med [!UICONTROL Live Mode], bara med [!UICONTROL Standard Mode]. Om du är i [!UICONTROL Live Mode] för en Standard Report Suite, men väljer [!UICONTROL Virtual report suite] i den här dialogrutan, visas standardläget när du klickar **[!UICONTROL OK]** här. Dessutom initieras kalenderkontrollen om för att matcha rapportsvitens kalendertyp (gregoriansk, återförsäljning, anpassad...). |
| **[!UICONTROL Page Name]** | Den sida som de här inställningarna gäller för. |
| **[!UICONTROL Language]** | Valet motsvarar de språk som erbjuds för Adobe Analytics. |
| **[!UICONTROL Label Overlays With]** | <ul><li>**[!UICONTROL No Label]**: Gäller endast för övertoningsövertäckningen. I det här fallet förmedlar övertäckningens färg en anledning till länkens rankning</li><li>**[!UICONTROL Value]**: summan för det råa måttet för den länken</li><li>**[!UICONTROL Percent]**: procent av måttet för den här länken för sidans totala mått.</li><li>**[!UICONTROL Rank]**: Länkens rangordning för alla länkar på den återgivna sidan</li></ul> |
| **[!UICONTROL Label Font Size]** | Gör att du kan öka/minska teckenstorleken för övertäckningsetiketten med ett reglage för bättre läsbarhet. |
| **[!UICONTROL Gradient/Bubble Color]** | Om du vill visa länkrankningar för övertoning eller bubbelövertäckning väljer du bland ett färgintervall. |
| **[!UICONTROL Color Gradient Based On]** | <ul><li>**[!UICONTROL Top 30 Rankings]**: Färgintensiteten har normaliserats för de 30 högsta värdena.</li><li>**[!UICONTROL Absolute Metric Value]**: Färgintensiteten är en funktion av det absoluta måttvärdet.</li></ul> |
| **[!UICONTROL Gradient Transparency]** | Välj genomskinlighetsnivå för övertoningsövertäckningarna. Den här inställningen påverkar inte [!UICONTROL Bubble]-övertäckningarna. |

## Standardinställningar {#section_24DB95376E1A448494ECF3F57743FC19}

De här inställningarna gäller för standardlägesövertäckningen.

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Dynamic Data Filtering]** | I den här listrutan kan du visa övertäckningar för<ul><li>(standard) Alla länkar på sidan</li><li>Den översta (översta) eller nedersta (nedersta) # rankade länkar på sidan, där # kan vara något av alternativen 1, 10, 50 eller 100.</li></ul> |
| **[!UICONTROL Hide overlays for links that received no hits]**. | En kryssruta som växlar synligheten för övertäckningar för länkar som inte har några data.<ul><li>(standard) Om kryssrutan är markerad visas ingen övertäckning när en länk inte har några ActivityMap-länkdata.</li><li>Om kryssrutan inte är markerad och en länk inte har några ActivityMap-länkdata, visas en övertäckning med etiketten &quot;-&quot;, vilket betyder N/A (ej tillämpligt). |

## Live-inställningar {#section_D30F6E62FB5D404090B588F396A460AF}

De här inställningarna gäller för live-lägesövertäckningen.

| Inställning | Beskrivning |
|---|---|
| **[!UICONTROL Display Top]** | Om du vill visa **[!UICONTROL Gainers]** eller **[!UICONTROL Losers]** (eller båda) som övertäckningar markerar du antalet länkar. |
| **[!UICONTROL Exclude bottom (%)]** | Välj det här alternativet om du vill ta bort Gainers-Losers-länkar med sparse-data. Filtrera ut den nedre procentandelen av länkändringar så att bara länkarna med tillräckligt med data visas för att visa relevanta vinster eller förluster. Procentandelen beräknas utifrån antalet länkar på den sidan. Om du till exempel filtrerar bort de nedre 10 % av en lista med 200 länkar filtreras de nedre 20 länkarna ut. |
| **[!UICONTROL Auto Update Data]** | Här kan du bestämma om Analytics-data som visas i gränssnittet automatiskt ska uppdateras när en ny period beräknas. |
| **[!UICONTROL Auto Update Period]** | När det här alternativet är markerat uppdateras webbsidan med varje ny datahämtning så att länkarna på sidan kan synkroniseras mer med de insamlade data. |
