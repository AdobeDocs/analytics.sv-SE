---
description: Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.
title: Aktivera integreringen
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Aktivera integreringen {#activate-the-integration}

Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.

1. Starta [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) och klicka **[!UICONTROL + Add New]** för att [lägga till en ny integrering](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. I **[!UICONTROL Show]** listan markerar du **[!UICONTROL By Name]** och drar [!DNL ~partnerintegreringen~] till en tom plugin-plats.
1. Slutför integreringsguiden med hjälp av informationen i följande tabell:

| Fält | Beskrivning |
|--- |--- |
| Report Suite | Rapportsviten som tar emot data från den här integreringen. |
| Integrationsnamn | Ange det integrationsnamn som Data Connectors visar i rapportsvitens lista över aktiv integrering. |
| Konto-ID | Ange ditt konto-ID för april. |
| Mottagar-ID | Detta ID är en kodad eller numerisk representation av en e-postadress från aprimosystemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsens mottagar-ID (kundöverläggningar, inköp osv.) som förs in i aprimosystemet och kan utnyttjas för återmarknadsföring. |
| Klickat | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar data som klickats via e-post och som importerats från e-postsystemet. Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. |
| Meddelande-ID | (Obligatoriskt) Lagrar det unika post-ID:t. |
| Öppnad | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postmeddelanden som öppnats från e-postsystemet. Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. |
| Mottagar-ID | (Obligatoriskt) Lagrar det unika besökar-ID:t. |
| Skickat | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar skickade e-postdata som importerats från e-postsystemet. Med händelsen Skickat kan du se hur många e-postmeddelanden som har skickats. |
| studsar | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postens Total Bounces-data som importerats från e-postsystemet. Med händelsen Total-Bounces kan du se antalet e-postmeddelanden som inte har levererats till mottagare på grund av ett leveransproblem. |
| Avbeställ | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postinformation om att avbryta prenumerationen som importerats från e-postsystemet. Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. |
| Segment | Den här integreringen skapar de partnerdefinierade segmenten som visas i avsnittet Partnersegment. Dessutom kan du välja befintliga segment på rapportsvitnivå som ska ingå i integreringen. |
| Åtkomstbegäranden | Aktivera de rekommenderade åtkomstbehörigheterna. |
| Datainsamling | Välj **JavaScript-plugin** om du vill använda plugin-programmet s_code.js som samlingsmodell för den här integreringen. |
Välj **Automatiserad lösning** om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen:
<ul><li>Frågesträngsparameter för meddelande-ID: Detta värde representerar det meddelande-ID som din e-postpartner har lagt till på landningssidans URL.</li>
<li>Frågesträngsparameter för mottagar-ID: Det här värdet representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL.</li></ul>||Instrumentpanel- och bokmärkesgenerering|Generera automatiskt en instrumentpanel och bokmärken för integreringen.|
