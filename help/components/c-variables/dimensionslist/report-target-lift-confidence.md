---
description: Gör att du kan bedöma hur framgångsrika kampanjer i Adobe Analytics är på samma sätt som du har gjort i Target Classic tidigare.
title: Måltavla för Lyft och förtroende
uuid: 00276cd2-2e0d-4a25-ae8a-d9f4b30dd8ba
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Måltavla för Lyft och förtroende

Gör att ni kan bedöma hur framgångsrika kampanjer i Adobe Analytics är på samma sätt som ni har gjort tidigare [!DNL Target Classic] .

**[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports]** > **[!UICONTROL Adobe Target]** > **[!UICONTROL Analytics for Target]** > **[!UICONTROL Target Activities]** .

Adobe Target-dokumentationen innehåller mer information om [Lyft](https://marketing.adobe.com/resources/help/en_US/target/target/c_estimating_lift_in_revenue.html) och [förtroende](https://marketing.adobe.com/resources/help/en_US/rec/c_Confidence_Level_and_Confidence_Interval.html).

Så här beräknar du Lyft och förtroende:

1. Klicka på en aktivitet i **[!UICONTROL Target Activities]** rapporten för att visa information om den.
1. Välj **[!UICONTROL Lift and Confidence]** under Typ av rapport.
1. Klicka **[!UICONTROL Show Metrics]** för att lägga till ett mått. Du kan inte lägga till mer än ett mått för den här typen av rapport, eftersom det är bäst att utvärdera ett test med bara ett mått. Fler mätvärden lägger bara till brus och minskar testsignalen.
1. (Valfritt) Under **[!UICONTROL Normalizing Metric]** väljer du något av följande: Besökare, besök eller exponeringar. Oftast är det här standardinställningen, Besökare.

1. Rapporten lägger till dessa mått, inklusive förhållandet mellan mätvärden och normaliseringsmått.

## Rapportinställningar {#section_3508439E09CA4E38B2EA309BA477C01D}

![](assets/lift_confidence_ui.png)

<table id="table_0FBB257C96454CDA82D487DC68459C13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Vald aktivitet </td> 
   <td colname="col2"> Den Target-aktivitet som du för närvarande visar och beräknar lyft och förtroende för. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ av rapportering </td> 
   <td colname="col2"> Här väljer du Lyft och förtroende - de visas som mått i rapportresultaten nedan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valda mått </td> 
   <td colname="col2"> Visar det mätvärde du valde (i exemplet ovan, Intäkter), det normaliserande måttet (unika besökare), förhållandet mellan dessa två mätvärden och sedan beräkningarna av Lyft och konfidens jämfört med Kontrollupplevelsen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nedbruten av </td> 
   <td colname="col2"> Du kan dela upp rapporten ytterligare genom andra rapporter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datafilter </td> 
   <td colname="col2"> Gör att du kan använda specifika filter på den här rapporten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normaliserar mått </td> 
   <td colname="col2"> Du kan normalisera med Besök, Besök eller Impressions. Det normaliserande måttet blir nämnaren för lyftberäkningen. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kontrollupplevelse </td> 
   <td colname="col2"> Den Target-upplevelse som du jämför och som du beräknar lyft för. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jämför med rapportsviten </td> 
   <td colname="col2"> Här kan du välja andra rapportsviter att jämföra med. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jämför med segment </td> 
   <td colname="col2"> Här kan du välja segment att jämföra med. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Procent visat som tal/diagram </td> 
   <td colname="col2"> Visar Lyft och konfidensprocent som ett tal eller ett diagram. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inkludera aktuella data </td> 
   <td colname="col2"> <p>Med alternativet Inkludera aktuella data i rapporter och analyser kan du visa de senaste Analytics-data, ofta innan data har bearbetats fullständigt och slutförts. Aktuella data visar de flesta mätvärden på några minuter och ger användbara data för snabba beslut. </p> </td> 
  </tr> 
 </tbody> 
</table>

