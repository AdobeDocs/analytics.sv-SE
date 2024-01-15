---
description: På sidan Sökmetoder visas hur olika sökmetoder rapporterar om konverteringsframgångar på din webbplats. Om en sökmotor till exempel refererar till en besökare till webbplatsen som gör ett köp, anger sökmetoderna hur sökmotorn får krediter för hänskjutningen.
title: Sökmetoder
feature: Admin Tools
role: Admin
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Sökmetoder

På sidan Sökmetoder visas hur olika sökmetoder rapporterar om konverteringsframgångar på din webbplats. Om en sökmotor till exempel refererar till en besökare till webbplatsen som gör ett köp, anger sökmetoderna hur sökmotorn får krediter för hänskjutningen.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**

## Hitta metodbeskrivningar {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Sökmetoden som du vill ändra </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allokering </td> 
   <td colname="col2"> Anger hur du ska kreditera en referens. Allokeringsalternativ som stöds är: <p> <span class="uicontrol"> Senaste (senaste): </span> Ger all kredit till den sista referenten (standard). </p> <p> <span class="uicontrol"> Originalvärde: </span> Ger all kredit till den första referenten. </p> <p> <span class="uicontrol"> Linjär: </span>Dividerar kredit mellan alla referenter lika. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Förfaller efter </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Besök: </span> Efter en angiven inaktivitetsperiod, vanligen cirka 30 minuter. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Sidvy: </span> Så snart en sida på webbplatsen öppnas. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minut: </span> Efter en minuts inaktivitet. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Köp: </span> Vid inköpstillfället. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Produktvy: </span> När en besökare tittar på en produktwebbsida. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Öppen kundvagn: </span> När en besökare öppnar en ny kundvagn online. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Kassa: </span> När en besökare checkar ut med en kundvagn online. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Kundvagn: </span> När en besökare lägger till en produkt i en kundvagn online. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Ta bort kundvagn: </span> När en besökare tar bort en produkt från en kundvagn online. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Öppen kundvagn: </span> När en besökare visar innehållet i en kundvagn online. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Alla sökmetoder upphör att gälla när besöket avslutas. Om du väljer att förfalla efter en annan händelse (t.ex. kundvagnsutcheckning) förfaller sökmetoden när kundvagnsutcheckning inträffar under besöket. Om en kundvagnsutcheckning inte inträffar under besöket förfaller ändå sökmetoden när besöket avslutas.
