---
description: Integreringsguiden för Data Connectors leder dig genom integreringsprocessen för Data Connectors.
title: Kör guiden Integrering av Data Connectors
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Kör guiden Integrering av Data Connectors{#running-the-data-connectors-integration-wizard}

Integreringsguiden för Data Connectors leder dig genom integreringsprocessen för Data Connectors.

Så här konfigurerar du integreringen:

1. Logga in på Experience Cloud.
1. På startsidan för Analytics klickar du på ikonen Data Connectors™ på hjulet eller verktygsfältet.
1. På sidan Data Connectors väljer du den Report Suite där du vill konfigurera integreringen.

   >[!NOTE]
   >
   >Se till att du väljer önskad rapportsvit i listrutan **Rapportsvit** i det övre vänstra hörnet på sidan Dataanslutningar.

1. Klicka på fliken **Alfabetisk** längst upp i **partnerlistan** till vänster i användargränssnittet för Data Connectors och leta sedan upp **Leverera** -ikonen.
1. Dra ikonen **Delivra** till en tom plugin-plats i Analytics-rapportsviten för att starta Data Connectors Integration Wizard.
1. Granska texten på introduktionssidan för Leverera-integrering och markera sedan kryssrutan för att acceptera de avgifter som är kopplade till integreringen. Klicka sedan på **Nästa**.

   På den här sidan finns en översikt över integreringen, tillsammans med praktiska länkar för mer information. Det finns både Adobe- och Delivra-avgifter för den här integreringen. Kontakta en säljare för båda organisationerna och se till att du förstår avgiftsstrukturen.
1. På varje sida i guiden för integrering av Data Connectors anger du den information som krävs enligt följande tabell:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>GUIDESIDAN #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FÄLT</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>BESKRIVNING</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Integrationsnamn </p> </td> 
   <td colname="col3"> <p>Ange det integrationsnamn som Data Connectors visar i rapportsvitens lista över aktiv integrering. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>E-postadress för integrering </p> </td> 
   <td colname="col3"> <p>Ange den e-postadress som tar emot alla meddelanden som rör den här integreringen och klicka sedan på <b>Nästa</b> för att gå vidare till steg 2 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Konto-ID </p> </td> 
   <td colname="col3"> <p>Ange ditt konto-ID (den unika identifierare som tilldelats din organisation av Delivra) och klicka sedan på <b>Nästa</b> för att gå vidare till steg 3 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Meddelande-ID </p> </td> 
   <td colname="col3"> <p>Identifiera den eVar-analys som används för att spåra e-postmeddelandets ID. </p> <p>Meddelande-ID används för marknadsförings-/återmarknadsföringskampanjer. Meddelande-ID kallas ofta"spårningskod". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Mottagar-ID </p> </td> 
   <td colname="col3"> <p>Identifiera den eVar-analys som används för att spåra e-postmottagarens ID. </p> <p>Mottagar-ID används för marknadsförings-/återmarknadsföringskampanjer. Meddelande-ID kallas ofta för"besökskod". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Kryssruta för godkännande </p> </td> 
   <td colname="col3"> <p>Granska informationen som visas bredvid kryssrutan Godkänn: </p> <p><i>Jag förstår att den här funktionen kan spåra personligt identifierbar information om våra webbplatsbesökare genom att aktivera spårning av mottagare-ID. Detta påverkar integriteten och kräver att min organisation implementerar lämpliga procedurer, som att meddela och samtycka till våra webbplatsbesökare. </i> </p> <p>Om du godkänner programsatsen för godkännande markerar du kryssrutan och klickar sedan på <b>Nästa</b> för att gå vidare till steg 4 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Klientdefinierade Report Suite-nivåsegment </p> </td> 
   <td colname="col3"> <p>Den här integreringen skapar de partnerdefinierade segmenten som visas till vänster på sidan Integreringssegment i Integreringsguiden. </p> <p>Dessutom kan du välja befintliga segment på rapportsvitnivå som ska ingå i integreringen. </p> <p>Markera önskade segment till höger på sidan och klicka sedan på <b>Nästa</b> för att gå vidare till steg 5 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Klickat </p> </td> 
   <td colname="col3"> <p>Ange den Analytics-händelse som lagrar data som klickats via e-post och som importerats från e-postsystemet. </p> <p>Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Öppnad </p> </td> 
   <td colname="col3"> <p>Ange den Analytics-händelse som lagrar e-postdata som har öppnats från e-postsystemet. </p> <p>Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Skickat </p> </td> 
   <td colname="col3"> <p>Ange den Analytics-händelse som lagrar skickade e-postdata som importerats från e-postsystemet. </p> <p>Med händelsen Klickat kan du se hur många e-postmeddelanden som har skickats. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Summa studsar </p> </td> 
   <td colname="col3"> <p>Ange den Analytics-händelse som lagrar e-postens Total Bounces-data som importerats från e-postsystemet. </p> <p>Med händelsen Total-Bounces kan du se antalet e-postmeddelanden som inte har levererats till mottagare på grund av ett leveransproblem. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Avbeställ </p> </td> 
   <td colname="col3"> <p>Ange den Analytics-händelse som lagrar e-postinformation om att avbryta prenumerationen som importerats från e-postsystemet. </p> <p>Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Aktier </td> 
   <td colname="col3"> <p>Ange hur många gånger e-postmeddelandet har delats till ett socialt nätverk och klicka sedan på <b>Nästa</b> för att gå vidare till steg 6 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Datainsamling: JavaScript-plugin </p> </td> 
   <td colname="col3"> <p>Välj <b>JavaScript-plugin</b> om du vill använda plugin-programmet som samlingsmodell för den här integreringen och klicka sedan på <b>Nästa</b> för att gå vidare till steg 7 i guiden. </p> <p> <p>Obs!  Den automatiserade lösningen är standardvalet. </p> </p> <p>Kontakta din Adobe-konsult för att få en kopia av JavaScript-pluginprogrammet som används för den här integreringen. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Datainsamling: Automatiserad lösning </p> </td> 
   <td colname="col3"> <p>Välj <b>Automatiserad lösning</b> om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. </p> <p> <p>Obs!  Den automatiserade lösningen är standardvalet. </p> </p> <p>Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen: </p> <p><b>Strängparameter för fråga-ID:</b>Det här värdet representerar det meddelande-ID som din e-postpartner har lagt till på startsidans URL. </p> <p><b>Frågesträngsparameter för mottagar-ID:</b> Detta värde representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL. </p> <p>Klicka på <b>Nästa</b> för att fortsätta till steg 7 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Integreringssammanfattning </p> </td> 
   <td colname="col3"> <p>Verifiera integreringsparametrarna genom att klicka på plustecknet (+) bredvid varje kategori och klicka sedan på <b>Spara</b> för att gå vidare till steg 8 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integreringen är klar </p> </td> 
   <td colname="col3"> <p>Klicka på <b>Slutför</b> för att slutföra integreringen. </p> <p><b>VIKTIGT!</b> Integreringsinställningarna sparas inte i Analytics förrän du klickar på <b>Slutför</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>
