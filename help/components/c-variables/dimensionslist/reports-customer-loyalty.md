---
description: Customer Loyalty avslöjar kundernas köpmönster.
title: Kundlojalitet
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Kundlojalitet

Customer Loyalty avslöjar kundernas köpmönster.

Rapporten visar kundernas köpmönster baserat på fyra kategorier av lojalitet:

* Inte en kund
* Ny kund
* Returkund
* Loyal Customer

Även om mätvärden som inte är inköpta kan visas i den här rapporten (t.ex. anpassade händelser, kundvagnshändelser och så vidare), baseras kategorierna alltid på antalet beställningar som görs. En besökare kan till exempel lägga till en anpassad händelse med namnet Interna sökningar i rapporten. Radposten visar hur många interna sökningar som gjorts av besökare som har gjort två inköp tidigare, inte antalet besökare som har gjort två interna sökningar. [!UICONTROL Return Customer]

**Bearbetning av kundlojalitet**

I följande tabeller definieras hur Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis och Data Warehouse för närvarande behandlar kundlojalitet:

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Efter 19 maj 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>21 april-19 maj 2016 </p> <p>(gäller inte datalager) </p> </th> 
   <th colname="col4" class="entry"> <p>Före 21 april 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inte en kund </p> </td> 
   <td colname="col2"> <p>Besökare som aldrig har köpt </p> </td> 
   <td colname="col3"> <p>Besökare som har gjort tio inköp till slutet av ett besök. </p> </td> 
   <td colname="col4"> <p>Inte tillgängligt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ny kund </p> </td> 
   <td colname="col2"> <p>Besökare som gjorde ett enstaka köp </p> </td> 
   <td colname="col3"> <p>Besökare som har gjort ett köp till slutet av besöket. </p> <p>(Om ett köp gjordes uppdaterades kundens status vid nästa besök efter köpet.) </p> </td> 
   <td colname="col4"> <p>Besökare som har gjort tio inköp till slutet av besöket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Returkund </p> </td> 
   <td colname="col2"> <p>Besökare som har gjort 2 inköp </p> </td> 
   <td colname="col3"> <p>Besökare som har gjort två inköp fram till slutet av besöket där de gjorde andra köpet. </p> <p>(Om ett köp gjordes uppdaterades kundens status vid nästa besök efter köpet.) </p> </td> 
   <td colname="col4"> <p>Besökare som har gjort ett köp till slutet av besöket där de gjorde köpet. </p> <p>(Om ett köp gjordes uppdaterades kundens status vid nästa besök efter köpet.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Loyal Customer </p> </td> 
   <td colname="col2"> <p>Besökare som har gjort mer än 3 inköp </p> </td> 
   <td colname="col3"> <p>Besökare som har gjort mer än tre köp fram till slutet av besöket där de gjorde det senaste köpet. </p> <p>(Om ett köp gjordes uppdaterades kundens status vid nästa besök efter köpet.) </p> </td> 
   <td colname="col4"> <p>Besökare som har gjort över 2 köp fram till slutet av besöket där de senast gjorde köpet. </p> <p>(Om ett köp gjordes uppdaterades kundens status vid nästa besök efter köpet.) </p> </td> 
  </tr> 
 </tbody> 
</table>

| version 14 Customer Loyalty (Current) |
|---|
| Ny kund | 1 besök och 1 köp |
| Returkund | Mer än 1 besök och 2 inköp |
| Loyal Customer | Mer än 1 besök och 3+ inköp |

Förmånsstatusen ändras direkt efter köphändelsen inom samma besök. Exempel: En ny kund (1 köp) gör ett köp och registrerar sig sedan för ett nyhetsbrev efter köpet inom samma besök. Nyhetsbrevets registreringshändelse betraktas som en kundinteraktion eftersom besökarens kundlojalitetstillstånd ändrades direkt efter köpet.
