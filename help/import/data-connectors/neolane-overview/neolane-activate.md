---
description: Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.
title: Aktivera integreringen
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
exl-id: d36c26ad-09c4-4a4d-a653-670c18f2ab19
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---

# Aktivera integreringen{#activate-the-integration}

Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.

1. Starta [Dataanslutningar](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) och klicka på **[!UICONTROL + Add New]** för att [lägga till en ny integrering](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. I listan **[!UICONTROL Show]** väljer du **[!UICONTROL By Name]** och drar integreringen [!DNL ~Partner~] till en tom plugin-plats.
1. Slutför integreringsguiden med hjälp av informationen i följande tabell:

| Fält | Beskrivning |
|--- |--- |
| Report Suite | Rapportsviten som tar emot data från den här integreringen. |
| Integrationsnamn | Ange det integrationsnamn som Data Connectors visar i rapportsvitens lista över aktiv integrering. |
| Klickat | Totalt antal e-postklick. |
| Kampanj-ID | Lagrar det unika meddelande-ID:t. Detta lagras ofta i kampanjvariabeln. |
| Öppnad | Totalt antal e-postöppningar. |
| Personklick | Antal personer som har klickat. |
| Behandlad | Totalt antal bearbetade e-postmeddelanden. |
| Broadlog ID | Detta ID är en kodad eller numerisk representation av en e-postadress från Neolane-systemet. Detta &quot;Broadlog ID&quot; är kopplat till besökares beteende längre fram i kedjan på webbplatsen (övergivna kundvagn med Broadlog ID, inköp osv.) som dras in i Neolane-systemet och kan utnyttjas för återmarknadsföring. |
| Schemalagd | Antal e-postmeddelanden som är schemalagda för leverans. |
| Skickat | Antal e-postmeddelanden som skickades. |
| Summa studsar | Antal e-postmeddelanden som inte har levererats till mottagarna på grund av ett leveransproblem. |
| Unika klick | Antal distinkta klick. |
| Unika öppningar | Antal distinkta öppningar. |
| Avbeställ | Antal besökare som öppnade e-postmeddelandet men sedan klickade på länken Avbeställ för att avanmäla framtida e-postmeddelanden från organisationen. |
| Segment | Den här integreringen skapar de partnerdefinierade segmenten som visas i avsnittet Partnersegment. Dessutom kan du välja befintliga segment på rapportsvitnivå som ska ingå i integreringen. |
| Åtkomstbegäranden | Aktivera de rekommenderade åtkomstbehörigheterna. |
| Datainsamling | Välj **JavaScript-plugin** om du vill använda plugin-programmet s_code.js som samlingsmodell för den här integreringen. Välj **Automatiserad lösning** om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen: <ul><li>Frågesträngsparameter för meddelande-ID: Detta värde representerar det meddelande-ID som din e-postpartner har lagt till på landningssidans URL.</li><li>Frågesträngsparameter för mottagar-ID: Det här värdet representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL.</li></ul> |
| Skapa kontrollpanel och bokmärke | Generera automatiskt en kontrollpanel och bokmärken för integreringen. |
