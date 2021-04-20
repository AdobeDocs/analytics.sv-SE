---
description: Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.
title: Målgrupper
uuid: bfe29dc8-8da8-4107-8bb1-4a7494f12bc9
feature: Reports & Analytics Basics & Analytics Basics
role: Business Practitioner, Administrator
exl-id: 6852e429-5b05-432c-bc6b-27f8c464dc50
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 1%

---

# Målgrupper

Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.

## Målgrupper {#concept_6516E81923E845198B7FC5D8F81DC35C}

Med målgrupperna kan ni mäta webbplatsens resultat och följa utvecklingen mot målmålen. Du kan till exempel vilja öka antalet besökare som kommer från en geografisk region, intäkterna per order eller antalet träffar som kommer från en viss hänvisare.

När du skapar mål väljer du vilka attributvärden eller eVars du vill mäta, eller så kan du välja att mäta hela webbplatsen mot det valda måttet.

Du kan till exempel mäta antalet unika besökare på webbplatsen och använda det som mål. I så fall väljer du hela webbplatsen. Men om du vill rikta in dig på antalet unika besökare på din webbplats från Chicago kan du ange den eVar i stället för att titta på hela webbplatsen.

## Målfältbeskrivningar {#section_44DFFB4A7AC54D65BC2345411686B2AD}

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.

Beskrivningar av fält och alternativ på [!UICONTROL Add/Edit Target]-sidan.

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
   <td colname="col2">Ange ett målnamn, som visas på sidan <span class="wintitle"> Målhanteraren</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd på </td> 
   <td colname="col2"> Gör att du kan tillämpa målet på hela platsen eller på ett markerat attribut eller eVar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Välj objekt </td> 
   <td colname="col2"> <p>Visar urvalsformuläret för det markerade attributet eller eVar, så att du kan utföra en avancerad sökning för relaterade objekt. Om du till exempel väljer eVar <span class="uicontrol"> Länder</span> kan du ange vilket land i objektlistan. Om du väljer eVar <span class="uicontrol"> Produkter</span> kan du ange vilken produkt i listan. Variabler för anpassade insikter visas också på menyn. Om du har ställt in en anpassad insiktsvariabel för att mäta besökares åldersintervall, visas sidintervallen i objektlistan, t.ex. 18-24, 25-35 osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mått </td> 
   <td colname="col2">Gör att du kan tillämpa målet på ett mätresultat. Den här menyn visar endast de mätvärden som gäller för en viss eVar. Om du t.ex. väljer <span class="uicontrol"> Produkter</span> som eVar gäller inte mått som <span class="uicontrol"> Sidan avslutas</span>. Måttet <span class="uicontrol"> Sidan avslutas</span> kan användas för en eVar på en webbsida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Period </td> 
   <td colname="col2"> <p>Gör att du kan definiera inställningarna <span class="uicontrol"> Datumintervall</span> och <span class="uicontrol"> Granularitet</span> för målet. Beroende på datumintervallets specifikationer gäller inte vissa granularitetsalternativ. När du anger värden för måtten anger du ett värde för varje granularitetsinställning. Om datumintervallet till exempel är februari-månaden och ditt val av granularitet är en vecka, anger du ett värde för varje vecka i februari-månaden. Målrapporter visas för varje granularitetsinställning. </p> </td> 
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
1. Klicka på **[!UICONTROL Add New]** på sidan [!UICONTROL Target Manager].
1. Konfigurera alternativen som beskrivs i [Beskrivning av målfält](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Klicka på **[!UICONTROL OK]**.

## Redigera ett mål {#task_946C558D2ECC4922ABD4A5A6183A095A}

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.
1. Klicka på ikonen **[!UICONTROL Edit]** i kolumnen **[!UICONTROL Manage]**.
1. Konfigurera alternativen som beskrivs i [Beskrivning av målfält](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Klicka på **[!UICONTROL OK]**.
