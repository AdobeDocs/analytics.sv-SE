---
description: 'null'
title: Vanliga frågor om Project Converter
uuid: 8e1bf0e9-ce0f-443a-bcfe-45d3e2c82b1c
translation-type: tm+mt
source-git-commit: 6a964f9ed9dcba6e4bf9eab8868ed325bc5e3560
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Vanliga frågor om Project Converter

>[!IMPORTANT]
>
>Adobe flyttar Ad Hoc Analysis till livets slut den 1 mars 2021. [Läs mer](https://adobe.ly/discoverworkspace)

## Vanliga frågor om Project Converter {#topic_8231595303AD403E9322645A63632D57}

* [Kända konverteringsproblem](/help/analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_39C922A58B2E49C9877B363042801361)
* [Vanliga frågor om konvertering](/help/analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_1E53FE373AF045978F939916124E194E)

## Kända konverteringsproblem {#section_39C922A58B2E49C9877B363042801361}

| Problem | Beskrivning |
|--- |--- |
| Minut granularitet med uppdelningar eller kolumner | Om du har använt minimala granulariteter eller om det finns minimala granulariteter i kolumner, kan projektet inte konverteras till Analysis Workspace.  Du kan komma runt problemet genom att ta bort detaljerna i minuterna och sedan konvertera projektet. Du kan sedan göra indelningar i Analysis Workspace. |
| Intern beräknad mätmetod används tillsammans med ett kolumnsegment | Om du använder ett internt beräknat mått tillsammans med ett kolumnsegment, kan projektet inte konverteras till Analysis Workspace. Du kan lösa problemet genom att ta bort interna beräknade värden från projektet före konverteringen och sedan lägga till dem igen i Analysis Workspace. |


## Vanliga frågor om konvertering {#section_1E53FE373AF045978F939916124E194E}

<table id="table_48CC119236C94835A6A512E989BE4200"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>F: Finns det några Ad Hoc Analysis-funktioner som inte stöds i Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>S: Site Analysis-rapporten stöds inte i Analysis Workspace. Det finns också vissa små skillnader mellan andra visualiseringar i Ad Hoc Analysis och Workspace. Se frågorna nedan för mer information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur konverteras tabellinställningar?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A645A004FB094A1593439A6607FE9A6B"> 
     <li id="li_033CA771F08A4BC3B0BC52CDCCA03FF4"><b>Antal rader som visas</b>: Arbetsytan är sidnumrerad så att endast 10 rader visas (kan anpassas så att upp till 400 rader visas i taget), medan Ad Hoc visar upp till 50 000 rader på en sida. Observera att data fortfarande finns i Workspace, som bara är sidnumrerade till standardvärdet 10 rader. </li> 
     <li id="li_A8B8890149334032A56D8D1C0F8691EA"><b>Avancerad sökning: </b>Flera samtidiga sökalternativ stöds inte, men ett enda sökalternativ (som <span class="wintitle"> Alla dessa ord</span>, <span class="wintitle"> den exakta frasen</span>, <span class="wintitle"> något av dessa ord</span>eller <span class="wintitle"> inget av dessa ord</span>) konverteras till Analysis Workspace. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur konverteras diagram och diagram?</b> </p> </td> 
   <td colname="col2"> <p>S: Observera att diagram och diagram kallas för"visualiseringar" i Workspace. </p> 
    <ul id="ul_597F5AB826EF434295D0CABD0313CAD5"> 
     <li id="li_AFB2805418034721A9519D999128C0A8"><b>Inställningar</b>: Visualiseringsinställningar som Antal objekt eller Antal fält stöds inte i Workspace. </li> 
     <li id="li_D5C7EA8815344EDB8585CBB8E1AF583E"><b>Cirkeldiagram</b>: Exporteras som en <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/donut.html"  > Donut</a> -visualisering. Den här visualiseringen i Workspace är begränsad till 19 avsnitt. </li> 
     <li id="li_91659FBFD77C4B3393D78447D658B7B4"><b>Bubbeldiagram</b>: Exporteras som en <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/scatterplot.html"  > Scatterplot</a> -visualisering. Som standard ritas det första måttet på x-axeln och det andra måttet på y-axeln. Om det bara finns ett mätvärde konverteras bubbeldiagram till linjevisualiseringar. </li> 
     <li id="li_FA05085FFB1747EBAF63616AC2B8D59C"><b>Histogram</b>: Stöder en annan låsningslogik i Workspace jämfört med Ad Hoc Analysis. Därför konverteras den till en <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/bar.html"  > Bar</a> -visualisering. </li> 
     <li id="li_959499D20796459CA0F6BBC8F0A8D808"><b>Punktdiagram</b>: I exporterade projekt i Analysis Workspace anges Y-axeln som den första kolumnen, X-axeln är den andra kolumnen och diametern är den tredje kolumnen. </li> 
     <li id="li_14E06D7A5106405A89A07B44FFD9A92D"><b>Utfallstabeller</b>: Högerklicka på kontrollpunkten och välj ett brytningsalternativ om du vill visa fallthrough- eller fallout-tabeller. </li> 
     <li id="li_240F43C386F04111A7632A8FCA37832C"><b>Datumintervall</b>på rapportnivå: Anpassade datumintervall för rapporter har inte tillämpats på utfallsvisualiseringar. </li> 
     <li id="li_1FF5B3FD9E424E7190AF03FD4DD9D654"><b>Flödesrapport</b>: Flödet flyttas till en separat panel för att bevara datumintervall och segmentering. Upprepade instanser kan inkluderas eller exkluderas under Flödesinställningar. </li> 
     <li id="li_BE8F8F6EC2EA49E18EF52539BC1700E0"><b>Konverteringstratt</b>: Konverteras till en friformstabell eftersom den inte stöds i Analysis Workspace. Utfallsvisualiseringen rekommenderas som ersättning för konverteringsfunktionen, men fungerar på ett något annorlunda sätt. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur konverteras segment?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_15D5B17461E2402DB07DF8B0A10AAC37"> 
     <li id="li_CF9C3D235A664B15B21D9F89DC5EF7D3">Segmenten är interna för det konverterade projektet (inte offentliga). Du kan välja att göra dem offentliga, så som visas här: <p><img placement="inline"  src="assets/internal_segment.png" id="image_5942392F18E845A5B41C3DED59374E89" width="300px" /> </p> </li> 
     <li id="li_AE61DAEC5C0047349DD192EFEEDB0BF9">Segment på arbetsytenivå i Ad Hoc Analysis används på projekt-/arbetsytenivå i Workspace. </li> 
     <li id="li_B1559E2C18724FE189AF87D0BEF16811">Ad Hoc Analysis rapportnivåsegment används på tabellkolumnnivå i Workspace. </li> 
     <li id="li_0E6DF6D44EA448A4A212BA2BB8E342CF">Ad Hoc Analysis tabellsegment används på tabellkolumnnivå i Workspace. </li> 
    </ul> <p>Du kan redigera segment i <a href="https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html"  > Segment Builder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur konverteras datumintervall?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A24AB597F3CE4847AF00D49A9A72A395"> 
     <li id="li_24FD18AF64114445939C4FBC03F2D406">Datumintervallet"förra X dagen" i Ad Hoc Analysis <i>exkluderar</i> idag, medan Analysis Workspace <i>inkluderar</i> idag. Därför kanske datumintervall som"Senaste 90 dagarna" inte matchar exakt mellan verktygen. Använd istället intervallet"Sista X <b>fullständiga </b> dagar" i Analysis Workspace. </li> 
     <li id="li_AA4390470C494748B4B12030B1226720">Datumintervallet på arbetsytans nivå i Ad Hoc Analysis tillämpas på projekt-/arbetsytenivån i arbetsytan. </li> 
     <li id="li_B8F0CDD413154856A315D087FEC4D418">Ad Hoc Analysis datumintervall på rapportnivå används på tabellkolumnnivå i Workspace. </li> 
    </ul> <p>Du kan redigera dina anpassade datumintervall under <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Components</span> &gt; <span class="uicontrol"> Date Ranges</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur konverteras beräknade mätvärden?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_ADA380D5D09B4223AAE4853D4C64F679"> 
     <li id="li_010572F793F54680ABE64117DAB7E800">Beräknade värden är interna för det exporterade projektet (inte offentliga). Du kan välja att göra dem offentliga genom att högerklicka på måttet och klicka på <span class="uicontrol"> Gör offentlig</span>. <p><img placement="inline"  src="assets/calc_metric_internal.png" id="image_EA19BA55B161499CBDB9275A5C94BA90" width="200px" /> </p> </li> 
     <li id="li_930546EC8FEB432C8810FAF93556FC9A">Alla typer av beräknade värden stöds för export. </li> 
     <li id="li_DFF7C6F8BB2344928D49194DA0F6EC38"><b>Allokeringstyper</b>: Även om Analysis Workspace inte uttryckligen visar allokeringstypen för ett beräknat mått skapas och matchas allokeringstypen som fanns i Ad Hoc Analysis. </li> 
    </ul> <p>Du kan redigera allokeringstypen i verktyget <a href="https://docs.adobe.com/content/help/sv-SE/analytics/components/calculated-metrics/cm-overview.html"  > Beräknad mätmetod</a> genom att klicka på ikonen Redigera (penna). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Hur används globala datainställningar i Ad hoc för konverterade projekt?</b> </p> </td> 
   <td colname="col2"> <p>Globala datainställningar kan göra att samma projekt som exporteras två gånger beter sig annorlunda: </p> 
    <ul id="ul_E3827883DD8045FAAB359D7E85E3EEFA"> 
     <li id="li_1056CA4813C44638BEB070228AE6914C"><b>Antal upprepningsinstanser.</b> Vilken inställning som än användes vid exporttillfället tillämpas på det exporterade projektet i Analysis Workspace. </li> 
     <li id="li_D5405E2862CF434CA82AA9DE000F4BBC"><b>Datakällor.</b> I Analysis Workspace visas alla analysdata, inklusive datakällor. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>F: Om mitt Ad Hoc Analysis-projekt är planerat, kommer schemat att omvandlas till Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>Nej, scheman konverteras inte. Öppna det projekt du vill schemalägga i Analysis Workspace och gå till <span class="uicontrol"> Dela</span> &gt; <span class="uicontrol"> Skicka fil i schema</span> för att konfigurera ett nytt schema. Se till att du avbryter ditt schemalagda projekt i Ad Hoc Analysis. </p> </td> 
  </tr> 
 </tbody> 
</table>

