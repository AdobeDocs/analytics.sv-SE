---
description: Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.
title: Ny rapportsvit – inställningar
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 2%

---


# Ny rapportsvit – inställningar

Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.

Beskrivningar av de element som används när [du skapar en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>I [Virtual Report Suite-dokumentationen](/help/components/vrs/c-workflow-vrs/vrs-create.md) visas hur du skapar virtuella rapportsviter.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rapportsvit-ID </span> </td> 
   <td colname="col2"> <p>Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte heller ändras. </p> <p>När du skapar flera rapportsviter måste du se till att namnkonventionen du använder garanterar unika ID:n för rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Platsrubrik</span> </td> 
   <td colname="col2">Identifierar rapportsviten i <span class="wintitle"> Admin Tools</span>. Den här titeln används också i listrutan <span class="wintitle"> Report Suite</span> i Suite-rubriken. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tidszon</span> </td> 
   <td colname="col2"> Schemalägger händelser och tidsstämpeldata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bas-URL</span> </td> 
   <td colname="col2"> (Valfritt) Definierar basdomänen för rapportsviten. URL-adressen fungerar som ett internt URL-filter om du inte uttryckligen definierar interna URL-filter för rapportsviten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Standardsida</span> </td> 
   <td colname="col2"> <p>(Valfritt) Tar bort förekomster av värdet för <span class="wintitle"> standardsida</span> från URL:er som upptäcks. Om rapporten med <span class="wintitle"> mest populära sidor</span> innehåller URL-adresser i stället för sidnamn, förhindrar den här inställningen att flera URL-adresser för samma webbsida används. </p> <p>URL-adresserna<span class="filepath"> https://mysite.com</span> och <span class="filepath"> https://mysite.com/index.html</span> är till exempel vanligtvis samma sida. Du kan ta bort överflödiga filnamn så att båda dessa URL-adresser visas som <span class="filepath"> https://mysite.com</span> i dina rapporter. </p> <p>Om du inte anger det här värdet tar Analytics automatiskt bort följande filnamn från URL:er: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span>default.html, -standard.cgi, -standard.asp, -hem.htm¥, -home.html¥, -home.cgiUnder och¥.asp¥. </p> <p>Om du vill inaktivera filnamnsborttagning anger du ett standardsidvärde som aldrig förekommer i dina URL-adresser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live Date </p> </td> 
   <td colname="col2">Informerar Adobe om det datum då du förväntar dig att den här rapportsviten ska aktiveras. Om ditt driftsättningsschema ändras kan du göra en uppdaterad trafikberäkning med hjälp av verktyget för permanent förväntad trafik <span class="wintitle"> i</span> trafikhantering <a href="/help/admin/c-traffic-management/traffic-management.md"></a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Beräknade sidvisningar per dag</span> </td> 
   <td colname="col2"> Identifierar det beräknade antalet sidvisningar som du förväntar dig att den här rapportsviten ska ha stöd för en dag. Stora trafikvolymer kräver en längre godkännandeprocess. För att undvika förseningar i bearbetningen bör denna uppskattning göras så korrekt som möjligt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Basvaluta</span> </td> 
   <td colname="col2"> <p>Anger standardvalutan som används för att lagra alla monetära data. Analytics-rapportering konverterar transaktioner i andra valutor till basvalutan med hjälp av den aktuella konverteringsgraden vid den tidpunkt då data tas emot. </p> <p> Analytics-rapportering använder JavaScript-variabeln <span class="varname"> currencyCode</span> för att identifiera valutan för en viss transaktion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Inaktivera stöd för flerbytetecken </span> </td> 
   <td colname="col2"> <p>Inaktiverar stöd för flerbytetecken för rapportsviten. Om du inaktiverar stöd för flerbytetecken antas data vara i ISO-8859-1-format. Webbsidorna måste ange sin teckenuppsättning i JavaScript-variabeln <span class="varname"> charSet</span> . </p> <p>Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter. </p> <p>Kontakta din kontoansvarige eller kundtjänst om du vill ändra stödet för flerbytetecken för en befintlig rapportsvit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Aktivera Ad Hoc Analysis för den här sviten</span> </td> 
   <td colname="col2"> Möjliggör visning av den här rapportsviten när du utför ad hoc analysis. </td> 
  </tr> 
 </tbody> 
</table>

