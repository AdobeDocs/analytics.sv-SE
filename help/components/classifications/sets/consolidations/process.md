---
title: Skapa och redigera klassificeringskonsolisioner
description: Beskriver hur du skapar, validerar, kör, godkänner och avbryter klassificeringskonsolideringar.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: ec49a5fd5771e4ca0a35ead681b556336bbc7031
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 0%

---

# Skapa och redigera klassificeringskonsolideringar

Konsolideringar av klassificeringsuppsättningar gör att du kan ta klassificeringar från flera datauppsättningar och kombinera dem till en. Använd det här gränssnittet för att skapa en konsolidering av klassificeringsuppsättningar från början till slut. Det här gränssnittet är mest värdefullt för organisationer som går från äldre klassificeringar till klassificeringsuppsättningar. De flesta organisationer som använder klassificeringsuppsättningar behöver troligen inte använda det här konsolideringsarbetsflödet.

## Skapa en konsolidering

Så här skapar du en klassificeringskonsolidering i Adobe Analytics huvudgränssnitt:

1. Välj **[!UICONTROL Classification sets]** på menyn **[!UICONTROL Components]**.
1. Välj fliken **[!UICONTROL Classification Sets]** i hanteraren för **[!UICONTROL Consolidations]**.
1. Välj **[!UICONTROL Classification Sets - Consolidations]** AddCircle![&#x200B; &#x200B;](/help/assets/icons/AddCircle.svg) i hanteraren för **[!UICONTROL New]**.
1. I dialogrutan **[!UICONTROL New Consolidation]**

   ![Klassificeringsuppsättningar - ny konsolidering](assets/classifications-sets-consolidations-new.png)
   1. Ange **[!UICONTROL Name]**. Till exempel: `Consolidation Example`.
   1. Ange **[!UICONTROL Description (optional)]**. Exempel: `Example classification set`.
   1. Ange en eller flera e-postadresser (kommaavgränsade) i **[!UICONTROL Notify of issues]**. E-postmeddelanden skickas till de här användarna om problem uppstår.
   1. Välj en klassificeringsuppsättning i listrutan **[!UICONTROL Classification Set To Match]**.

      Den vänstra listan **[!UICONTROL Source Classification Set]** är ifylld med klassificeringsuppsättningar som liknar den valda klassificeringslistan och som är tillgängliga för konsolidering.

   1. Välj de klassificeringsuppsättningar som du vill konsolidera i den vänstra listan och släpp de markerade uppsättningarna i den högra listan under den markerade ![Key](/help/assets/icons/Key.svg) **[!UICONTROL _klassificeringsuppsättningen_]**.

      Du kan flytta enskilda och markerade klassificeringsuppsättningar i listan. Du kan också ersätta ![Key](/help/assets/icons/Key.svg) **[!UICONTROL _klassificeringsuppsättningen_]** med en vald klassificeringsuppsättning genom att dra och släppa.

   1. Välj **[!UICONTROL Save]** om du vill spara klassificeringskonsolideringen. Välj **[!UICONTROL Cancel]** om du vill avbryta.

När en klassificeringskonsolidering har sparats valideras den automatiskt för konsolidering. Valideringen säkerställer att varje enskild klassificeringsuppsättning är giltig för denna konsolidering. När posten lyckades visas statusen **[!UICONTROL Validated]** i konsolideringslistan för klassificeringar.

När du har skapat en konsolidering är nästa steg:

* [Verifiera om](#re-validate) klassificeringskonsolideringen när du har gjort ändringar i den ursprungliga konfigurationen.
* [Kör](#run) klassificeringskonsolideringen.
* [Godkänn](#approve) klassificeringskonsolideringen.



<!--
         
  

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

-->

## Redigera en konsolidering

Så här redigerar du en klassificeringskonsolidering i huvudgränssnittet i Adobe Analytics:

1. Välj **[!UICONTROL Classification sets]** på menyn **[!UICONTROL Components]**.
1. Välj fliken **[!UICONTROL Classification Sets]** i hanteraren för **[!UICONTROL Consolidations]**.
1. I hanteraren för **[!UICONTROL Classification Sets Consolidations]**:
   1. Välj namnet på din klassificeringskonsolidering. Dialogrutan **[!UICONTROL Consolidation: _Konsolideringsnamn för klassificering_]** visas. Utseendet och tillgängliga åtgärder beror på konsolideringens aktuella status och om du fortfarande har möjlighet att ändra klassificeringskonsolideringen.

      | Tillgängliga åtgärder | Beskrivning |
      |---|---|
      | ![Avbryt](/help/assets/icons/Cancel.svg) **[!UICONTROL Cancel]** | [Avbryt konsolideringen](#cancel). |
      | ![Markering](/help/assets/icons/Checkmark.svg) **[!UICONTROL Re-Validate]** | [Verifiera konsolideringen](#re-validate) igen. |
      | ![Spela upp](/help/assets/icons/Play.svg) **[!UICONTROL Run]** | [Kör konsolideringen](#run). |
      | ![ThumbUp](/help/assets/icons/ThumbUp.svg) **[!UICONTROL Approve]** | [Godkänn konsolideringen](#approve). |



### Validera igen

Du kan validera en klassificeringskonsolidering på nytt i dialogrutan Konsolidering: klassificeringskonsolidering. En ![avisering](/help/assets/icons/Alert.svg) kan innehålla ytterligare information om problem med din konsolidering som kräver att konsolideringen konfigureras om.

![Klassificeringsuppsättningar - Konsolidering - Verifiera igen](assets/classifications-sets-consolidations-validated.png)

Så här validerar du klassificeringskonsolideringen:

1. Konfigurera om konsolideringen med samma dra och släpp-gränssnitt som du använde för att skapa konsolideringen.
1. Välj ![bock](/help/assets/icons/Checkmark.svg) **[!UICONTROL Re-Validate]**. Valideringen säkerställer att varje enskild klassificeringsuppsättning är giltig för denna konsolidering. När det är klart visas ett popup-meddelande: ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Successfully submitted consolidation for validation!]**
1. Stäng dialogrutan genom att välja ![CrossSize400](/help/assets/icons/CrossSize400.svg). Eller välj ![Spela upp](/help/assets/icons/Play.svg) Kör för att köra konsolideringen eller ![Avbryt](/help/assets/icons/Cancel.svg) för att avbryta klassificeringen.



<!--
Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

-->

### Kör

När en klassificeringskonsolidering har validerats kan du köra konsolideringen.

Så här kör du en klassificeringskonsolidering:

1. Välj ![Spela upp](/help/assets/icons/Play.svg) **[!UICONTROL Run]**. Ett popup-meddelande visar ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Successfully submitted consolidation for processing!]**
1. Stäng dialogrutan genom att välja ![CrossSize400](/help/assets/icons/CrossSize400.svg).


### Godkänn

När en klassificeringskonsolidering har körts är konsolideringsstatusen **[!UICONTROL Waiting for Approval]**. Godkännandet av en klassificeringskonsolidering ersätter de enskilda klassificeringsuppsättningarna med den konsoliderade klassificeringsuppsättningen och de enskilda klassificeringsuppsättningarna tas bort.

![Klassificeringsuppsättningar - Konsolidering väntar på godkännande](assets/classifications-sets-consolidations-waitingforapproval.png)

Så här godkänner du en konsolidering av klassificeringsuppsättningar:

1. Använd **[!UICONTROL Similarity Reports]** för att granska konsolideringen. Den här rapporten innehåller en tabell med följande kolumner:

   * **[!UICONTROL Classification Set Name]**: Namnet på klassificeringsuppsättningen.
   * **[!UICONTROL Mismatch]**: Procentandelen rader där nyckelvärden inte matchar källklassificeringsuppsättningen. Om felmatchningsprocenten är hög kan felmatchningen vara en indikation på att klassificeringsdata är för olika. Kontrollera att de valda klassificeringsuppsättningarna har liknande klassificeringsdata.
   * **[!UICONTROL Absent]**: Procentandelen rader där nyckelvärden finns i klassificeringsuppsättningen ![&#x200B; Key](/help/assets/icons/Key.svg) men inte i källklassificeringsuppsättningen. Alla rader som inte finns läggs till i den konsoliderade klassificeringsuppsättningen.

1. Om klassificeringskonsolideringen är klar för godkännande väljer du ![bock](/help/assets/icons/Checkmark.svg) **[!UICONTROL Approve]**. En **[!UICONTROL Approve Consolidation?]**-dialogruta ber om bekräftelse. Välj **[!UICONTROL Approve]** för att godkänna konsolideringen. Välj **[!UICONTROL Cancel]** om du vill avbryta.

När den har godkänts skapas den konsoliderade klassificeringsuppsättningen. Status är inställd på **[!UICONTROL Complete]**.


### Avbryt

Du kan avbryta en klassificeringskonsolidering innan godkännande.

Så här avbryter du en klassificeringskonsolidering:

1. Välj **[!UICONTROL Cancel]**.

   Du kan inte återuppta en konsolidering när konsolideringen har avbrutits.
1. Välj **[!UICONTROL Cancel Consolidation]** om du vill avbryta konsolideringen. Välj **[!UICONTROL Go Back]** om du vill återställa annulleringen.
