---
description: Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.
title: Aktivera integreringen
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Aktivera integreringen{#activate-the-integration}

Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.

1. Starta [Data Connectors](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html) och klicka **[!UICONTROL + Add New]** för att [lägga till en ny integrering](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. I **[!UICONTROL Show]** listan markerar du **[!UICONTROL By Name]** och drar [!DNL ~partnerintegreringen~] till en tom plugin-plats.
1. Slutför integreringsguiden med hjälp av informationen i följande tabell:

| Fält | Beskrivning |
|--- |--- |
| Report Suite | Rapportsviten som tar emot data från den här integreringen. |
| Integrationsnamn | Ange det integrationsnamn som Data Connectors visar i rapportsvitens lista över aktiv integrering. |
| Integration-UUID | Ange ditt API för DreamMail-integrering. |
| Klientnamn | Ange ditt DreamMail-klientnamn. |
| Platsnamn | Ange ditt DreamMail-webbplatsnamn. |
| Studsa bakgrunder | Antal e-postmeddelanden som inte har levererats till mottagarna på grund av ett leveransproblem. |
| Levererat | Antal slutförda meddelandeleveranser. |
| Leveransfel | Misslyckade meddelandeleveranser. |
| HTML-öppnas | Antal besökare som öppnade e-postmeddelandet. |
| Ogiltiga | Antal ogiltiga e-postadresser. |
| Campaign | Marknadsföringskampanj-ID. |
| Godkänn | Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. |
| eVar för e-post | En e-postadress från DreamMail-systemet. Den här e-postadressen är kopplad till besökares beteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som dras in i DreamMail-systemet och kan utnyttjas för återmarknadsföring. |
| Spotlight-händelse | Händelse som kan exporteras i segment för återmarknadsföring. |
| Spotlight-inköp | Händelse som kan exporteras i segment för återmarknadsföring. |
| Värde för spotlight | Intäktshändelse som kan exporteras i segment för återmarknadsföring. |
| TotalClicks | Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. |
| Segment | Den här integreringen skapar de partnerdefinierade segmenten som visas i avsnittet Partnersegment. Dessutom kan du välja befintliga segment på rapportsvitnivå som ska ingå i integreringen. |
| Åtkomstbegäranden | Aktivera de rekommenderade åtkomstbehörigheterna. |
| Datainsamling | Välj **JavaScript-plugin** om du vill använda plugin-programmet s_code.js som samlingsmodell för den här integreringen (se ). Välj **Automatiserad lösning** om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen:<ul><li>Frågesträngsparameter för meddelande-ID: Detta värde representerar det meddelande-ID som din e-postpartner har lagt till på landningssidans URL.</li><li>Frågesträngsparameter för mottagar-ID: Det här värdet representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL.</li></ul> |
| Skapa kontrollpanel och bokmärke | Generera automatiskt en kontrollpanel och bokmärken för integreringen. |
