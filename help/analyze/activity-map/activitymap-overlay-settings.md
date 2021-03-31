---
description: På inställningspanelen Activity Map kan du ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar.
title: Konfigurera inställningar för Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---


# Konfigurera inställningar för Activity Map

På inställningspanelen Activity Map kan du ändra inställningar och egenskaper för alla typer av övertäckningsvisualiseringar.

Gå till inställningspanelen Activity Map genom att klicka på kugghjulsikonen i verktygsfältet Activity Map.

På inställningspanelen visas olika innehåll baserat på det valda programläget. Fliken Annan innehåller allmänna inställningar.

| Standard | **[!UICONTROL Gradient]** eller  **[!UICONTROL Bubble]** övertäckningar |
|---|---|
| Live | **[!UICONTROL Gainers & Losers]**,  **[!UICONTROL Gradient]**,  **[!UICONTROL Bubble]** övertäckningar |
| Övriga | Val av rapportsvit och språkval |

## Inställningar för standardlägesövertäckning {#section_24DB95376E1A448494ECF3F57743FC19}

![](assets/settings_standard.png)

<table id="table_0244107DE6D142F2A1DA4882E0ED9826"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Inställningar </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Etikettera övertäckningar med</span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>Ingen etikett</b>: endast för övertoningsövertäckningen. I det här fallet ger övertäckningens färg en känsla för länkens rankning </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Värde</b>: länkens totala rådatamått </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Procent</b>: procentandelen av måttet för länken för sidans totala mått. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Rankning</b>: Länkens rangordning för alla länkar på den återgivna sidan </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Teckenstorlek för etikett</span> </td> 
   <td colname="col3"> Gör att du kan öka/minska teckenstorleken för övertäckningsetiketten med ett reglage för bättre läsbarhet. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Visa</span> </td> 
   <td colname="col3">Välj <span class="uicontrol"> Överkant</span>, <span class="uicontrol"> Underkant</span> eller <span class="uicontrol"> Alla länkar</span> som ska visas i övertäckningen. Om du väljer Överkant eller Underkant måste du också välja hur många länkar som ska visas. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Dölj övertäckningar för länkar som inte fått några träffar.</span> </td> 
   <td colname="col3"> Med den här kryssrutan kan du dölja övertäckningar för länkar som inte fått några träffar för att få bättre ordning i gränssnittet. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Övertoningsfärg / Bubbelfärg</span> </td> 
   <td colname="col3">Välj mellan ett färgintervall om du vill visa länkrankningar för övertäckning för övertoningar <span class="uicontrol"> Övertoning</span> eller <span class="uicontrol"> Bubbla</span> övertäckningsvisualiseringar. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Färgövertoning baserad på</span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> Top 30 Rankings</span>: Färgintensiteten normaliseras för de 30 översta värdena. </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Absolut måttvärde</span>: Färgintensiteten är en funktion av det absoluta måttvärdet. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Genomskinlighet för övertoning</span> </td> 
   <td colname="col3">Välj genomskinlighetsnivå för övertoningsövertäckningarna. <p>Den här inställningen påverkar inte bubbelövertäckningarna. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inställningar för live-lägesövertäckningar {#section_D30F6E62FB5D404090B588F396A460AF}

![](assets/settings_live.png)

| Inställningar | Beskrivning |
|---|---|
| **[!UICONTROL Display Top]** | Välj antalet länkar som ska visas (eller alla) och **[!UICONTROL Gainers]** eller **[!UICONTROL Losers]** (eller båda) som ska visas som övertäckningar. |
| **[!UICONTROL Exclude bottom (%)]** | Välj det här alternativet om du vill ta bort Gainers-Losers-länkar med sparse-data. Filtrera ut den nedre procentandelen av länkändringar så att bara länkarna med tillräckligt med data visas för att visa relevanta vinster eller förluster. Procentandelen beräknas utifrån antalet länkar på den sidan. Om du t.ex. filtrerar bort de nedre 10 % av en lista med 200 länkar filtreras de sista 20 länkarna ut. |
| **[!UICONTROL Auto Update Data]** | Här kan du bestämma om Analytics-data som visas i gränssnittet ska uppdateras automatiskt när en ny period beräknas, eller inte. |
| **[!UICONTROL Auto Update Period]** | När det här alternativet är markerat uppdateras webbsidan med varje ny datahämtning så att länkarna på sidan kan synkroniseras mer med de insamlade data. |

## Andra inställningar {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Report Suite </td> 
   <td colname="col2"> <p>Listan med rapportsviter som är tillgängliga för dig är inte längre begränsad till de rapportsviter som definieras i webbsidestaggen. Nu kan du ersätta den valda rapportsviten (som motsvarar en av taggarna på sidan) med en annan rapportserie. Den här nya rapportsviten behöver inte länkas till en tagg på sidan. Om du ändrar den markerade rapportsviten i inställningarna för Activity Map uppdateras alla berörda analysrapporter om du väljer <span class="uicontrol"> Spara</span>-processen. </p> <p> <p>Viktigt: Virtuella rapportsviter är inte kompatibla med Live-läge, endast med standardläge. Om du är i Live-läge för en standardrapportsserie, men väljer en virtuell rapportserie i den här dialogrutan, visas standardläget när du klickar på <span class="uicontrol"> OK</span> här. </p> </p> <p>Dessutom initieras kalenderkontrollen om så att den matchar rapportsvitens kalendertyp (gregoriansk, återförsäljning, anpassad...). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Språk </td> 
   <td colname="col2"> Valet motsvarar de språk som erbjuds för Adobe Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Om </td> 
   <td colname="col2"> Anger programmets namn och versionsnummer. </td> 
  </tr> 
 </tbody> 
</table>

