---
description: Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.
title: Målgrupper
topic: Reports and analytics
uuid: bfe29dc8-8da8-4107-8bb1-4a7494f12bc9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Målgrupper

Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.

## Målgrupper {#concept_6516E81923E845198B7FC5D8F81DC35C}

Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.

När du skapar mål väljer du vilka attributvärden eller eVars du vill mäta, eller så kan du välja att mäta hela webbplatsen mot det valda måttet.

Du kan till exempel mäta antalet unika besökare på webbplatsen och använda det som mål. I så fall väljer du hela webbplatsen. Men om du vill rikta in dig på antalet unika besökare på din webbplats från Chicago kan du ange den eVar i stället för att titta på hela webbplatsen.

## Målfältbeskrivningar {#section_44DFFB4A7AC54D65BC2345411686B2AD}

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.

Beskrivningar av fält och alternativ på [!UICONTROL Add/Edit Target] sidan.

<table id="table_E08728BECC204DF59F0AC99957A68CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Målnamn </td> 
   <td colname="col2">Ange ett målnamn som visas på sidan <span class="wintitle"> för målhanteraren</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd på </td> 
   <td colname="col2"> Gör att du kan tillämpa målet på hela platsen eller på ett markerat attribut eller eVar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Välj objekt </td> 
   <td colname="col2"> <p>Visar urvalsformuläret för det markerade attributet eller eVar, så att du kan utföra en avancerad sökning för relaterade objekt. Om du till exempel väljer eVar- <span class="uicontrol"> länder</span>kan du ange vilket land i objektlistan. Om du väljer eVar- <span class="uicontrol"> produkter</span>kan du ange vilken produkt i artikellistan. Variabler för anpassade insikter visas också på menyn. Om du har ställt in en anpassad insiktsvariabel för att mäta besökares åldersintervall, visas sidintervallen i objektlistan, t.ex. 18-24, 25-35 osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mått </td> 
   <td colname="col2">Gör att du kan tillämpa målet på ett mätresultat. Den här menyn visar endast de mätvärden som gäller för en viss eVar. Om du t.ex. väljer <span class="uicontrol"> Produkter</span> som eVar gäller inte mått som <span class="uicontrol"> Sidutträde</span> . Måttet <span class="uicontrol"> Sidan avslutas</span> kan användas på en webbsida som eVar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Period </td> 
   <td colname="col2"> <p>Här kan du definiera inställningarna för <span class="uicontrol"> datumintervall</span> och <span class="uicontrol"> granularitet</span> för målet. Beroende på datumintervallets specifikationer gäller inte vissa granularitetsalternativ. När du anger värden för måtten anger du ett värde för varje granularitetsinställning. Om datumintervallet till exempel är februari-månaden och ditt val av granularitet är en vecka, anger du ett värde för varje vecka i februari-månaden. Målrapporter visas för varje granularitetsinställning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Värden </td> 
   <td colname="col2"> <p>Här kan du ange målvärden för tidsperioden och det valda måttet. Det här värdet är de målnummer som du försöker nå. Om målet till exempel baserades på intäkter, och du planerade 10 000 USD i intäkter för en viss månad, skulle du ange 10 000 i värdefältet för månaden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lägg till ett mål {#task_94915391E26E4F808F2538AA92BC7E71}

Steg som beskriver hur du lägger till ett mål.

<!-- 

t_add_a_target.xml

 -->

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.
1. På [!UICONTROL Target Manager] sidan klickar du på **[!UICONTROL Add New]**.
1. Konfigurera alternativen som beskrivs i [Målfältbeskrivningar](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Klicka på **[!UICONTROL OK]**.

## Redigera ett mål {#task_946C558D2ECC4922ABD4A5A6183A095A}

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.
1. Klicka på **[!UICONTROL Manage]** ikonen i **[!UICONTROL Edit]** kolumnen.
1. Konfigurera alternativen som beskrivs i [Målfältbeskrivningar](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Klicka på **[!UICONTROL OK]**.
