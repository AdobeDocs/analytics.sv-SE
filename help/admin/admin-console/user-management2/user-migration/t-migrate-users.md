---
description: Migrera användare från det äldre användarhanteringssystemet Analytics till Admin Console.
title: Migrera Analytics-användarkonton för Adobe ID:n
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 6%

---

# Migrera Analytics-användarkonton för Adobe ID:n{#migrate-analytics-user-accounts-for-adobe-ids}

Migrera användare från det äldre användarhanteringssystemet Analytics till Admin Console.

## Migrera Analytics-användarkonton för Adobe ID:n {#task-f3355f3b14a340feae58cfa04c0ba1c9}

Migrera användare från det äldre användarhanteringssystemet Analytics till Admin Console.

>[!NOTE]
>
>Om en administratör som inte är inloggad via Experience Cloud försöker få åtkomst till migreringsverktyget för användar-ID dirigeras de om till inloggningssidan för Experience Cloud.

**Migrera Analytics-användare**

1. Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.

   ![](/help/admin/admin-console/user-management2/user-migration/assets/migration-progress.png)

   Sidan Migrering av användar-ID har två avsnitt: *Migreringsförlopp* och *Användarinformation*.

   **Migreringsförlopp**

   <table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Fas </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Migreringar har slutförts </p> </td> 
      <td colname="col2"> <p>Användarna accepterade inbjudan. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Äldre inloggning inaktiverad </p> </td> 
      <td colname="col2"> <p>Äldre inloggning med ett företags-ID är inaktiverad. Användare kommer nu åt Experience Cloud via sina Adobe ID eller Enterprise ID. När alla användare har nått den här fasen har migreringen slutförts. </p> <p>I migreringen är den gamla inloggningen inaktiverad. Användarna omdirigeras till <span class="filepath"> experience.loud.adobe.com</span> och måste logga in med Adobe ID eller Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

   **Användarinformation**

   Användarinformation visar användarna i organisationen, avgränsade med domännamn.

   <table id="table_3822E27AF81E4A188562FEB5131548A5"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Element </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Domän </p> </td> 
      <td colname="col2"> <p>Domäner är specifika för e-post-ID:n för den aktuella Analytics-användarbasen. En domän kan bara tas i anspråk av en enda organisation, och bara systemadministratörer kan göra anspråk på en domän. Mer information finns i <a href="https://helpx.adobe.com/enterprise/help/request-access-to-claimed-domain.html"> Begär åtkomst till en domän som tagits i anspråk</a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Domänen har tagits i anspråk </p> </td> 
      <td colname="col2"> <p>Om du vill migrera användare som Enterprise ID eller Federated ID måste du vara systemadministratör och göra anspråk på en tillgänglig domän via Adobe Admin Console innan du migrerar användare. Läs mer <a href="https://helpx.adobe.com/enterprise/help/identity.html"> här</a>. </p> <p>Om du inte vill göra anspråk på domäner för Enterprise ID eller Federated ID hoppar du över det här steget och migrerar användare som Adobe ID. Läs mer om ID-typer <a href="https://helpx.adobe.com/enterprise/help/identity.html"> här</a>. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Leta reda på domänen som innehåller de användar-ID som du vill migrera, under **[!UICONTROL Requiring Migration]**, klicka **[!UICONTROL Select Users]**.
1. På [!DNL Users] väljer du de användare du vill migrera och klickar sedan på **[!UICONTROL Migrate]**.

   När du klickar **[!UICONTROL Migrate]**, får användarna en inbjudan (migreringen initierad) och måste acceptera den. Den här åtgärden flyttar användar-ID:t till migreringen slutförd. Du kan sedan stänga av deras tidigare åtkomst till `[!DNL my.omniture.com].`

   ![](/help/admin/admin-console/user-management2/user-migration/assets/user-info.png)

1. Ange vilken typ av ID du vill migrera användarna (Adobe ID eller Enterprise ID)

   Efter migrering av användare ändras statusen under kolumnmigreringsstatusen från *`Not Initiated`* till *`Migrated`*.

   If *`Failed`* visas, hovra över ikonen om du vill ha en beskrivning av varför migreringen misslyckades.
