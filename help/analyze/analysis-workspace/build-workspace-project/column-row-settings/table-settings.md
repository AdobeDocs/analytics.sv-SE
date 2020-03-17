---
description: Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.
title: Radinställningar
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 5c2f2d098398927d8379f2eb9ea69ca9acbfd726

---


# Radinställningar

Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.

Du kan också använda [högerklicksåtgärder i en tabell](/help/analyze/analysis-workspace/visualizations/freeform-table.md) för att hantera markerade rader.

Om du vill komma åt tabellradsinställningarna klickar du på inställningsikonen bredvid en dimension, ett segment, ett mått, en tidsperiod eller en uppdelning i var och en av dessa:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Radinställning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Datumjämförelser</a> </p> </td> 
   <td colname="col2"> <p><b>Justera datum från varje kolumn så att alla börjar på samma rad. </b> </p> <p>När du väljer att justera datumen, till exempel i en månadsjämförelse mellan oktober och september 2016, börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Inaktiverad som standard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Procenttal </p> </td> 
   <td colname="col2"> <p><b>Beräkna procentandelar per rad</b> </p> <p>Tvingar friformstabellen att beräkna cellprocenten över raden i stället för nedåt i kolumnen. Detta är särskilt användbart för att hantera procentsatser. Den är som standard aktiverad när du använder ikonen <span class="uicontrol"> Visa</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kolumnsummor </p> </td> 
   <td colname="col2"> <p>De här inställningarna visas bara med <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md"  > manuella (statiska) rader</a> (när du har markerat en begränsad uppsättning med objekt), inte med dynamiska rader (när du släpper i en dimension som visar alla objekt). <p>Obs! För <i>metriska</i> manuella rader är inställningen inaktiverad eftersom det inte är rimligt att summera mått förutom de aktuella raderna i en tabell. </p> </p> <p><b>Beräkna summor genom att summera de värden som finns i varje kolumn (aktiverat som standard):</b> </p> <p>Med det här alternativet beräknas endast de rader som finns i tabellen. (Beräkning på klientsidan) </p> <p><b>Beräkna summor baserat på alla rader för varje mätvärde (inaktiverat som standard):</b> </p> <p>Det här alternativet inkluderar alla dimensionsartiklar för den här dimensionen, även de som inte finns med i tabellen. (Beräkning på serversidan) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdelningar </p> </td> 
   <td colname="col2"> <p><b>Uppdelning efter position:</b> </p> <p>Du kan utföra uppdelningar baserat på en fast plats i en frihandstabell. Du kan till exempel ange att de sju översta raderna alltid ska brytas ned. </p> <p>(Tidigare var listan med värden i neddelningen "låst". Detta ledde till en situation där du, om du t.ex. bröt ned <span class="term"> Datum</span> för <span class="term"> sida</span>, fick en lista över de 50 översta sidorna för det valda datumintervallet. Om du sparade rapporten och sedan körde den en månad senare, hade troligen de 50 översta sidorna ändrats. Analyarbetsytan använder dock resultaten från den ursprungliga uppdelningen och returnerar samma sidor, men med den aktuella månaden som datumintervall.) </p> <p>Så här utför du uppdelningar baserade på en fast plats: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Dela upp några av raderna i tabellen. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Klicka på ikonen Inställningar (kugghjulet) bredvid tabellraden som du vill ha i fast position. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Markera kryssrutan bredvid <span class="uicontrol"> Uppdelning efter position</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Ändra sorteringsordningen eller datumintervallet och lägg märke till att uppdelningarna nu är knutna till radpositionen, inte till de hårdkodade raderna. </li> 
    </ol> <p>Inaktiverad som standard. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Radinställning | Beskrivning |
|--- |--- |
| Datumjämförelser | Justera datum från varje kolumn så att alla börjar på samma rad.   När du väljer att justera datumen, till exempel i en månadsjämförelse mellan oktober och september 2016, börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september.<br>Inaktiverad som standard. |
| Procenttal | Beräkna procentandelar per rad Tvingar fram friformstabellen för att beräkna cellprocenten över raden i stället för nedåt i kolumnen. Detta är särskilt användbart för att hantera procentsatser.<br>Aktiveras som standard när du använder ikonen Visualisera. |
| Kolumnsummor | De här inställningarna visas bara med [statiska rader](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) (när du har markerat en begränsad uppsättning med objekt), inte med dynamiska rader (d.v.s. när du släpper i en dimension som visar alla objekt).<ul><li>**[!UICONTROL Show sum of current rows as the total]** - här visas en summa av raderna i tabellen på klientsidan, vilket innebär att summan **inte** kan deduplicera mått som besök eller besökare.</li><li>**[!UICONTROL Show Grand Total]** - detta visar en summa på serversidan, vilket innebär att summan kommer att ta bort dubbletter av statistik som besök eller besökare.</li></ul> |
| Uppdelningar | **[!UICONTROL Breakdown by position]**:  Du kan utföra uppdelningar baserat på en fast plats i en frihandstabell. Du kan till exempel ange att de sju översta raderna alltid ska brytas ned.<br>(Tidigare var listan med värden i neddelningen &quot;låst&quot;. Detta ledde till en situation där du, om du t.ex. bröt ned Datum för sida, fick en lista över de 50 översta sidorna för det valda datumintervallet. Om du sparade rapporten och sedan körde den en månad senare, hade troligen de 50 översta sidorna ändrats. Analyarbetsytan använder dock resultaten från den ursprungliga uppdelningen och returnerar samma sidor, men med den aktuella månaden som datumintervall.)<br>Så här utför du uppdelningar baserade på en fast plats: 1. Dela upp några av raderna i tabellen. 2. Klicka på ikonen Inställningar (kugghjulet) bredvid tabellraden som du vill ha i fast position. 3. Markera kryssrutan bredvid Uppdelning efter position. 4. Ändra sorteringsordningen eller datumintervallet och lägg märke till att uppdelningarna nu är knutna till radpositionen, inte till de hårdkodade raderna.<br>Inaktiverad som standard. |