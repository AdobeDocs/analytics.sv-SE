---
description: Integreringsguiden för Data Connectors leder dig genom integreringsprocessen för Data Connectors.
title: Silverpop-integrering
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Silverpop-integrering{#silverpop-integration}

Integreringsguiden för Data Connectors leder dig genom integreringsprocessen för Data Connectors.

Så här konfigurerar du integreringen:

1. I Adobe Experience Cloud väljer du Data Connectors™ i listan över produkter.
1. Klicka **[!UICONTROL Add New]** och välj **[!UICONTROL By Name]** i **[!UICONTROL Show]** listrutan.
1. Hitta ikonen **Silverpop Engage 2.0** och dra den till en tom plugin-plats i Analytics-rapportsviten för att starta Data Connectors Integration Wizard.
1. Granska texten på introduktionssidan för Silverpop-integrering och markera sedan kryssrutan för att acceptera de avgifter som är associerade med integreringen.
1. Välj den rapportsvit som du vill använda för den här integreringen.
1. Ange ett eget namn för att identifiera integreringen och klicka sedan på **[!UICONTROL Create and Configure this Integration]**.

   På den här sidan finns en översikt över integreringen, tillsammans med praktiska länkar för mer information. Det finns både Adobe- och Silverpop-avgifter kopplade till den här integreringen. Kontakta en säljare för båda organisationerna och se till att du förstår avgiftsstrukturen.
1. På varje sida i guiden för integrering av Data Connectors anger du den information som krävs enligt följande tabell:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Fält</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Konfigurationsavsnitt</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Beskrivning</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Integrationsnamn </p> </td> 
   <td colname="col03"> <p>(1) Integreringsinställningar </p> </td> 
   <td colname="col3"> <p>Ange det integrationsnamn som Data Connectors visar i rapportsvitens lista över aktiv integrering. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Hämta fil </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p> För användning vid återmarknadsföring av filnedladdning. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> E-postadress </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>Används för återmarknadsföring till besökare utan ett känt Silverpop-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Konto-ID </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>Ange ditt Silverpop-konto-ID (den unika identifierare som din organisation tilldelats av Silverpop) och klicka sedan på <b>Nästa</b> för att gå vidare till steg 3 i guiden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Formulärnamn </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>För användning vid återmarknadsföring av blankettinlämning. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Utskicks-ID </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop-ID </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> studsar </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) Ange den Analytics-händelse som lagrar e-postens Total Bounces-data som importerats från e-postsystemet. </p> <p>Med händelsen Total-Bounces kan du se antalet e-postmeddelanden som inte har levererats till mottagare på grund av ett leveransproblem. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Klickat </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) Ange den Analytics-händelse som lagrar data som importerats från e-postsystemet och klickats. </p> <p>Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Filen har hämtats </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p> För användning vid återmarknadsföring av filnedladdning. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formuläret har fyllts i </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>För användning vid återmarknadsföring av blankettinlämning. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formuläret har startats </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>För användning vid återmarknadsföring av blankettinlämning. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Öppnad </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) Ange den Analytics-händelse som lagrar e-postmeddelanden som öppnats från e-postsystemet. </p> <p>Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Skickat </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) Ange den Analytics-händelse som lagrar skickade e-postdata som importerats från e-postsystemet. </p> <p>Med händelsen Skickat kan du se hur många e-postmeddelanden som har skickats. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Avbeställ </p> </td> 
   <td colname="col03"> <p>(2) Variabelmappningar </p> </td> 
   <td colname="col3"> <p>(Obligatoriskt) Ange den Analytics-händelse som lagrar e-postinformation om att avbryta prenumeration som importerats från e-postsystemet. </p> <p>Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segment </p> </td> 
   <td colname="col03"> <p>(3) Datainställningar </p> </td> 
   <td colname="col3"> <p>Den här integreringen skapar de partnerdefinierade segmenten som visas i avsnittet Partnersegment. </p> <p>Dessutom kan du välja befintliga segment på rapportsvitnivå som ska ingå i integreringen. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Åtkomstbegäranden </p> </td> 
   <td colname="col03"> <p>(3) Datainställningar </p> </td> 
   <td colname="col3"> <p> (Obligatoriskt) Aktivera <span class="uicontrol"> Tillåt den här integreringen att hämta produktdata</span>. </p> <p>Valfritt: Tillåt den här integreringen att ladda ned intäkter, order och enheter. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Datainsamling </p> </td> 
   <td colname="col03"> <p>(3) Datainställningar </p> </td> 
   <td colname="col3"> <p>Välj <b>JavaScript-plugin</b> om du vill använda plugin-programmet s_code.js som samlingsmodell för den här integreringen (se <a href="../silverpop-overview/silverpop-analytics-code.md"> Analytics Plug-In Code</a>). </p> <p>Välj <b>Automatiserad lösning</b> om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. </p> <p>Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen: </p> <p> <b>Strängparameter för fråga-ID:</b>Det här värdet representerar det meddelande-ID som din e-postpartner har lagt till på startsidans URL. </p> <p> <b>Frågesträngsparameter för mottagar-ID:</b> Detta värde representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Skapa kontrollpanel och bokmärke </p> </td> 
   <td colname="col03"> <p>(4) Rapportinställningar </p> </td> 
   <td colname="col3"> <p>Generera automatiskt en kontrollpanel och bokmärken för integreringen. </p> </td> 
  </tr> 
 </tbody> 
</table>

