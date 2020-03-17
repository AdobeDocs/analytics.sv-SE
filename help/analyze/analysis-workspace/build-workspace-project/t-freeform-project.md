---
description: Skapa ett projekt och lägg till komponenter (mått, mått, segment, datumintervall) på frihandspanelen.
keywords: Analysis Workspace
title: Skapa ett arbetsyteprojekt
topic: Reports and analytics
uuid: c1def77a-a76e-4699-9feb-1ede5b70b7ba
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Skapa ett arbetsyteprojekt

Skapa ett projekt och lägg till komponenter (mått, mått, segment, datumintervall) på frihandspanelen.

I den här artikeln får du information om gränssnittselementen för Analysis Workspace och hur du skapar ett projekt. Specifika användningsexempel finns i [Användningsexempel för arbetsytan](/help/analyze/analysis-workspace/freeform-analysis-examples-use-cases.md)Analys.

## Skapa ett projekt

1. Ange användarbehörighet för att skapa och strukturera projekt.

   Innan du skapar eller strukturerar ett Analysis Workspace-projekt måste administratören lägga till dig i en grupp med aktiverad **[!UICONTROL Create / Curate Projects in Analysis Workspace]** behörighet eller i **[!UICONTROL All Report Access]** användargruppen. ( **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [Grupper](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)).

1. Klicka [!DNL Experience Cloud]på **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   Du kan också ange ett snedstreck (/) för att öppna rapportens sökfält och sedan skriva *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Klicka på **[!UICONTROL Create New Project]**.

   Du kan välja om du vill skapa ett projekt från

* Ett tomt projekt (standard). Instruktioner finns nedan.
* En standardmall. Mallarna skapas av Adobe och skickas ut direkt. Instruktioner finns i [Mallar](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)
* En anpassad mall. De här mallarna skapas av användare med administratörsbehörighet. Instruktioner finns i [Mallar](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)

   ![](assets/start_modal.png)

1. Om du vill skapa ett projekt från ett tomt projekt klickar du på **[!UICONTROL Blank Project]**.

   * Klicka sedan **[!UICONTROL Create]** eller
   * Klicka bara **[!UICONTROL Enter]**.
   Ett tomt projekt visas med en friformspanel och en datatabellvisualisering.

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >Ibland visas meddelandet&quot;Inkompatibel rapportserie&quot; när du läser in ett projekt (eller byter till en rapportsvit) där inte alla komponenter (mått/mått) som ingår i projektet ingår i rapportsviten. Du kan se en lista över komponenter som inte är kompatibla, så att du vet varför du får meddelandet.

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > Komponenter</a> </td> 
   <td colname="col2"> <p>Dimensioner, mätvärden, segment och datumintervall som du kan dra in i projekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualiseringar</a> </td> 
   <td colname="col2"> <p>Objekt som du kan dra till panelen eller projektområdena i gränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  > Frihandspanelen </a> </td> 
   <td colname="col2"> <p>Arbetsytan eller arbetsytan som du interagerar med i Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Spara projektet. Ge projektet ett namn, ange en beskrivning (valfritt, men användbart) och tagga projektet (valfritt) och klicka sedan på **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. Du kan nu högerklicka och kopiera en visualisering eller panel och sedan klistra in (&quot;infoga&quot;) det kopierade elementet på en annan plats i projektet eller i ett annat projekt.

   Du kan använda den här funktionen för att skapa&quot;byggstenar&quot; - fördefinierade visualiseringar/paneler - som kan kopieras till andra projekt för att komma igång snabbare, med data som är specifika för ditt företag.

   >[!NOTE]
   >
   >När du har kopierat/sparat som är länkar nu relativt till det projekt de bor i, inte det ursprungliga projektet som de kopierades från.

## Lägg till komponenter och visualiseringar {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Bygg ditt projekt genom att dra *`components`* och *`visualizations`* till projektet.

   **Komponenter**

   I verktygsfältet Komponent visas sökbara mått, mått, segment och datumintervall som du använder oftast.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponent </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensioner (orange) </td> 
   <td colname="col2"> <p>Använd på projektnivå </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#, eVar# och event# läggs till i dimensionsnamnen och du kan söka på dessa tal. Exempel: "Internal Campaign" visas i det vänstra fältet som "Internal Campaign (evar2)". </p> <p> Observera att prop-, eVar- och händelsenumren inte visas i tabellen (för att titlarna ska vara korta). </p> <p>Det finns en standardsorteringsordning för vissa färdiga dimensioner, när de dras till en friformstabell eller när de visas i den vänstra listen. När"Timme på dagen" släpps till exempel i ett bord eller visas i det vänstra fältet sorteras det från 12:00-11:00. Du kan fortfarande sortera efter en måttkolumn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrisk (grön) </td> 
   <td colname="col2"> <p>Använd på projektnivå. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Förekomster</span> är datatabellens standardmått. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segment (blå) </td> 
   <td colname="col2"> <p>Det går bara att dra på panelnivå, men du kan skapa textbundna segment i datatabellen. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>Mer information finns i <a href="/help/analyze/analysis-workspace/freeform-analysis-examples-use-cases.md"  > Använd ärenden för arbetsytan</a> Analys. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datumintervall och detaljrikedom (lila) </td> 
   <td colname="col2"> <p>Kan endast dras på panelnivå. Du kan skapa ett projekt från kalendern när du konfigurerar ett datumintervall. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

Panelen innehåller [!UICONTROL Visualizations] standarddiagram för analyser, diagram, donuts, datatabeller, [kohorttabeller](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) , Venndiagram osv. Du kan dra och släppa flera visualiseringar i ditt projekt.

![Stegresultat](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Steg

## Använd högerklicksmenyn för att anpassa data {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

Med högerklicksmenyn kan du utföra följande åtgärder, beroende på vilken cell i en tabell du högerklickar på.

![Stegresultat](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Åtgärd </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Lägg till tidsperiodkolumn</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Jämför tidsperioder</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kopiera till Urklipp </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta bort markerade </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > Skapa avisering från markering</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > Uppdelning</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Dimensioner </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Mått </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Segment </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Tid </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualisera</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > Hämta som CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/analysis-workspace-features.md"  > Trendval</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > Skapa segment från markering</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"  > Kör i segmentjämförelse</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa endast markerade rader </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa alla rader </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Information om hur du kopierar och väljer rader finns i [Tangentbords- och musinteraktioner på arbetsytan](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) för analyser.
