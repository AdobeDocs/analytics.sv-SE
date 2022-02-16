---
description: Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.
title: Ny rapportsvit – inställningar
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# Ny rapportsvit – inställningar

Du kan skapa en ny rapportserie genom att välja en fördefinierad mall eller genom att använda en av dina befintliga rapportsviter som modell.

Beskrivningar av de element som används vid [skapa en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>The [Dokumentation för Virtual Report Suite](/help/components/vrs/c-workflow-vrs/vrs-create.md) visar hur du skapar virtuella rapportsviter.

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
   <td colname="col2"> <p>Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte ändras. </p> <p>När du skapar flera rapportsviter måste du se till att namnkonventionen du använder garanterar unika ID:n för rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Platsrubrik</span> </td> 
   <td colname="col2">Identifierar rapportsviten i <span class="wintitle"> Administratörsverktyg</span>. Den här titeln används också i <span class="wintitle"> Report Suite</span> nedrullningsbar lista i Suite-rubriken. </td> 
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
   <td colname="col2"> <p>(Valfritt) Ränder på förekomster av <span class="wintitle"> Standardsida</span> värde från URL:er som upptäcks. Om <span class="wintitle"> Mest populära sidor</span> rapporten innehåller URL:er i stället för sidnamn. Den här inställningen förhindrar flera URL:er för samma webbsida. </p> <p>URL:erna<span class="filepath"> https://example.com</span> och <span class="filepath"> https://example.com/index.html</span> är vanligtvis samma sida. Du kan ta bort överflödiga filnamn så att båda dessa URL:er visas som <span class="filepath"> https://example.com</span> i era rapporter. </p> <p>Om du inte anger det här värdet tar Analytics automatiskt bort följande filnamn från URL:er: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span>och<span class="filepath"> home.asp</span>. </p> <p>Om du vill inaktivera filnamnsborttagning anger du ett standardsidvärde som aldrig förekommer i dina URL-adresser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live Date </p> </td> 
   <td colname="col2">Informerar Adobe om vilket datum du förväntar dig att den här rapportsviten ska aktiveras. Om ditt distributionsschema ändras kan du göra en uppdaterad trafikberäkning med hjälp av <span class="wintitle"> Permanent förväntad trafik</span> verktyg in <a href="/help/admin/c-traffic-management/traffic-management.md"> Trafikhantering</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Beräknade sidvisningar per dag</span> </td> 
   <td colname="col2"> Identifierar det beräknade antalet sidvisningar som du förväntar dig att den här rapportsviten ska ha stöd för en dag. Stora trafikvolymer kräver en längre godkännandeprocess. För att undvika förseningar i bearbetningen bör denna uppskattning göras så korrekt som möjligt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Basvaluta</span> </td> 
   <td colname="col2"> <p>Anger standardvalutan som används för att lagra alla monetära data. Analysrapporter konverterar transaktioner i andra valutor till basvalutan med hjälp av den aktuella konverteringsgraden vid den tidpunkt då data tas emot. </p> <p> Analysrapporter använder <span class="varname"> currencyCode</span> JavaScript-variabel som identifierar valutan för en viss transaktion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Inaktivera stöd för flerbytetecken </span> </td> 
   <td colname="col2"> <p>Inaktiverar stöd för flerbytetecken för rapportsviten. Om du inaktiverar stöd för flerbytetecken antas data vara i ISO-8859-1-format. Webbsidorna måste ange teckenuppsättningen i <span class="varname"> charSet</span> JavaScript-variabel. </p> <p>Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter. </p> <p>Kontakta din kontoansvarige eller kundtjänst om du vill ändra stödet för flerbytetecken för en befintlig rapportsvit. </p> </td> 
  </tr>  
 </tbody> 
</table>
