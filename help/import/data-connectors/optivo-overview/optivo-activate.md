---
description: Använd konfigurationsguiden för Adobe Data Connectors för att konfigurera integreringen.
title: Aktivera integreringen
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
exl-id: 18fb2f55-f1fb-4d97-bd1e-8c5e74dbde69
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

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
| E-postadress | Ange en e-postadress för att ta emot integreringsrelaterad information. |
| Konto-ID | Detta är den unika identifierare som din e-postleverantör har tilldelat din organisation. Det kommer att användas när kampanjdata för e-post begärs (t.ex. # Skickat, # Öppnat, # Klickat osv.) från och skicka besökarsegment till din e-postleverantör. |
| Mottagar-ID | Detta ID är en kodad eller numerisk representation av en e-postadress från optivo®-sändningssystemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som läggs in i optivo®-sändningssystemet och kan utnyttjas för återmarknadsföring. |
| Meddelande-ID | (Obligatoriskt) Lagrar det unika post-ID:t. Dessa klassificeringsdimensioner skapas av guiden för dataanslutningar för meddelande-ID: <br>a)**Kampanjer**: Kampanjer som är associerade med meddelandet. <br>b)**Kanal**: Sändningskanalen, det här är ständigt&quot;optivo-utsändning&quot;. <br>c)**Landskod**: Det här fältet innehåller landskoden för avsändarlandet. Det är en konstant&quot;DE&quot;. <br>d)  **Leveransverktyg**: Överföringsmetod, alltid&quot;E-post&quot;.<br> e)  **Meddelandenamn**: Namnet på utskicket så som det är konfigurerat i optivo®-utskick. <br>f)  **Startdatum**: Tidsstämpel för början av det här utskicket. |
| Tid för postklick | (Obligatoriskt) Detta krävs för att överföra information om en mottagaråtgärd till optivo®-utskick efter att mottagaren klickat på en länk i ett utskick. |
| Post Click Product | (Obligatoriskt) Detta krävs för att överföra information om en mottagaråtgärd till optivo®-utskick efter att mottagaren klickat på en länk i ett utskick. |
| Åtgärden Publicera klickning | (Obligatoriskt) Detta krävs för att överföra information om en mottagaråtgärd till optivo®-utskick efter att mottagaren klickat på en länk i ett utskick. |
| Hård studs | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar hårddiskstudsdata som importerats från e-postsystemet. Antal e-postmeddelanden som inte levererats till mottagarna och som betraktas som permanent olevererbara. |
| Mjuk studs | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar mjuka studsar som importerats från e-postsystemet. Antal e-postmeddelanden som inte har levererats till mottagarna på grund av ett leveransproblem. |
| Klickat | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postklickade data som importerats från e-postsystemet. Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. |
| Öppnad | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postöppnade data som importerats från e-postsystemet. Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. |
| Skickat | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar skickade e-postdata som importerats från e-postsystemet. Med händelsen Skickat kan du se hur många e-postmeddelanden som har skickats. |
| Avbeställ | (Obligatoriskt) Ange den Adobe Analytics-händelse som lagrar e-postinformation om att avbryta prenumerationen som importerats från e-postsystemet. Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. |
| Segment | Aktivera befintliga segment som ska användas tillsammans med den här integreringen (valfritt). |
| Åtkomstbegäranden | Aktivera de rekommenderade åtkomstbehörigheterna. |
| Datainsamling | Välj **JavaScript-plugin** om du vill använda plugin-programmet s_code.js som samlingsmodell för den här integreringen. Välj **Automatiserad lösning** om du vill använda en automatiserad samlingsmodell för den här integreringen och ange sedan de unika identifierare som används för den här integreringen. Om du väljer det här alternativet anger du de unika identifierare som används för den här integreringen:<ul><li>Frågesträngsparameter för meddelande-ID: Detta värde representerar det meddelande-ID som din e-postpartner har lagt till på landningssidans URL.</li><li>Frågesträngsparameter för mottagar-ID: Det här värdet representerar det mottagar-ID som din e-postpartner har lagt till på landningssidans URL.</li></ul> |
| Skapa kontrollpanel och bokmärke | Generera automatiskt en kontrollpanel och bokmärken för integreringen. |
