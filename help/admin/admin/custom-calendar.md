---
description: Kalenderalternativ i andra format än den gregorianska modellen. Alternativen är kalendermodellerna 4-4-5, 4-5-4 och 5-4-4, som alla används som standard för detaljhandeln. Dessutom erbjuder rapportering ett alternativ för en helt anpassningsbar kalender som du kan konfigurera själv.
title: Anpassa kalender
feature: Administratörsverktyg
uuid: 4e5e538b-54c9-4c2f-8b6c-9f91b6c7bcc7
exl-id: 2196c7b7-7183-43a8-bb91-5a1e479819d4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Anpassa kalender

Kalenderalternativ i andra format än den gregorianska modellen. Alternativen är kalendermodellerna 4-4-5, 4-5-4 och 5-4-4, som alla används som standard för detaljhandeln. Dessutom erbjuder rapportering ett alternativ för en helt anpassningsbar kalender som du kan konfigurera själv.

**[!UICONTROL Admin]** >  **[!UICONTROL Report Suites]** > Välj rapportserie >  **[!UICONTROL Edit Settings]** >  **[!UICONTROL General]** >  **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>Om du ändrar kalendern ändras det sätt som data behandlas på (dvs. definitionen av unika besökare varje vecka och månad). När en kalenders definition av veckor och månader ändras, ändras inte historiska data. Den här inställningen påverkar även segment som baseras på datumintervall.

Du kan använda kalendern för att definiera den första dagen i veckan och året eller använda ett annat återförsäljningsformat. Kalenderformaten används för olika syften, inklusive försäljningsjämförelse och prognosstandardisering, lönekostnadsanalys eller reglering av fysiskt lagerantal. Detaljhandeln använder till exempel räkenskapskalendern för 4-5-4 som stöd för försäljningssäsongens särdrag i detaljhandeln. Varje kalenderformat beskrivs nedan.

## Anpassa kalenderbeskrivningar {#section_B0D224DACB914A378902A4E0E1234889}

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
   <td colname="col2"> <p> Använder den traditionella gregorianska kalendern men du kan välja den första månaden på året och den första dagen i veckan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 butikskalender </p> </td> 
   <td colname="col2"> <p> Varje månad delas upp med antalet veckor i månaden. Betydelse: Januari har fyra veckor och så vidare. National Retail Federation använder kalenderformatet 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anpassad kalender </p> </td> 
   <td colname="col2"> <p> Erbjuder tre format baserat på antalet veckor varje månad. Antalet veckor i varje månad beror på den valda första dagen på året. </p> <p>Ett år har 52 veckor. Dela upp det i 4 kvartal så får du 13 veckor per kvartal. Men det finns tre månader på en kvart. 13 är inte delbart med tre, så det slutar med att du sätter den extra veckan i en av månaderna så att den alltid är konsekvent. 5/4/4 betyder att den första månaden i kvartalet har den extra veckan. 4/5/4 betyder att den andra månaden har den extra veckan osv. I kalendern 5-4-4 läggs den 53:e veckan till på årets sista kvartal. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: Januari har fyra veckor, februari har fem veckor, mars har fyra veckor och så vidare. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: Januari har fyra veckor, februari har fyra veckor, mars har fem veckor och så vidare. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-4-4</b>: Januari har fem veckor, februari har fyra veckor, mars har fyra veckor och så vidare. </li> 
    </ul> <p>Obs!  Det här kalenderalternativet stöds i alla Adobe Analytics-verktyg (Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map) utom för Data warehouse, som inte har stöd för anpassade kalendrar. </p> </td> 
  </tr> 
 </tbody> 
</table>
