---
description: Report Builder använder den anpassade Analytics-kalendern. Du kan använda kalendern för att definiera den första dagen i veckan och året eller använda ett annat återförsäljningsformat. Kalenderformaten används för olika syften, inklusive försäljningsjämförelse och prognosstandardisering, lönekostnadsanalys eller reglering av fysiskt lagerantal.
title: Anpassad kalender
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
source-git-commit: 244af34b463ea5df55eaca31f3b2df4ada552b5d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Anpassad kalender

Report Builder använder den anpassade Analytics-kalendern. Du kan använda kalendern för att definiera den första dagen i veckan och året eller använda ett annat återförsäljningsformat. Kalenderformaten används för olika syften, inklusive försäljningsjämförelse och prognosstandardisering, lönekostnadsanalys eller reglering av fysiskt lagerantal.

Varje kalenderformat beskrivs nedan.

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kalender </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gregoriansk kalender </p> </td> 
   <td colname="col2"> <p> Använder det traditionella kalenderformatet (januari till december, med 30 eller 31 dagar och ett varierande antal veckor i varje månad). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändrad gregoriansk kalender </p> </td> 
   <td colname="col2"> <p> Använder den traditionella gregorianska kalendern, men du kan välja den första månaden på året och den första dagen i veckan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 butikskalender </p> </td> 
   <td colname="col2"> <p> Varje månad delas upp med antalet veckor i månaden. Betydelse: Januari har fyra veckor och så vidare. The National Retail Federation använder kalenderformatet 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassad kalender </p> </td> 
   <td colname="col2"> <p> Erbjuder tre format baserat på antalet veckor varje månad. Antalet veckor i varje månad beror på den valda första dagen på året. </p> <p>Ett år har 52 veckor. Dela upp det i 4 kvartal så får du 13 veckor per kvartal. Men det finns tre månader på en kvart. 13 är inte delbart med tre, så det slutar med att du sätter den extra veckan i en av månaderna så att den alltid är konsekvent. 5/4/4 betyder att den första månaden i kvartalet har den extra veckan. 4/5/4 betyder att den andra månaden har den extra veckan osv. I kalendern 5-4-4 läggs den 53:e veckan till på årets sista kvartal. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>:Januari har fyra veckor, februari har fem veckor, mars har fyra veckor och så vidare. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: Januari har fyra veckor, februari har fyra veckor, mars har fem veckor och så vidare. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: Januari har fem veckor, februari har fem veckor, mars har fyra veckor och så vidare. </li> 
    </ul> <p>Obs! Det här kalenderalternativet stöds i alla Adobe Analytics-verktyg: Analysis Workspace, Report Builder och Activity Map. Undantaget är Data Warehouse som inte har stöd för anpassade kalendrar. </p> </td> 
  </tr> 
 </tbody> 
</table>
