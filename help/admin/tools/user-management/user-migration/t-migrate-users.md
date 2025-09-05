---
description: Migrera användare från det äldre användarhanteringssystemet Analytics till Admin Console.
title: Migrera användarkonton för Analytics för Adobe ID:n
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---

# Migrera användarkonton för Analytics för Adobe ID:n

Migrera användare från det äldre användarhanteringssystemet Analytics till Admin Console.

>[!NOTE]
>
>Om en administratör som inte är inloggad via Experience Cloud försöker få åtkomst till migreringsverktyget för användar-ID dirigeras de om till inloggningssidan för Experience Cloud.

1. Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User ID Migration]**.

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   Migreringssidan för användar-ID har två avsnitt: *Migreringsförlopp* och *Användarinformation*.

## Migreringsförlopp

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
      <td colname="col2"> <p>Äldre inloggning med ett företags-ID är inaktiverad. Användare kommer nu att få tillgång till Experience Cloud via sin Adobe ID eller Enterprise ID. När alla användare har nått den här fasen har migreringen slutförts. </p> <p>I migreringen är den gamla inloggningen inaktiverad. Användare omdirigeras till <span class="filepath"> experience.adobe.com</span> och måste logga in med Adobe ID eller Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Användarinformation

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
   <td colname="col2"> <p>Domäner är specifika för e-post-ID:n för den aktuella Analytics-användarbasen. En domän kan bara tas i anspråk av en enda organisation, och bara systemadministratörer kan göra anspråk på en domän. Mer information finns i <a href="https://helpx.adobe.com/se/enterprise/help/request-access-to-claimed-domain.html"> Begär åtkomst till en domän som tagits i anspråk </a>. </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>Domänen har tagits i anspråk </p> </td> 
   <td colname="col2"> <p>Om du vill migrera användare som Enterprise ID eller Federated ID måste du vara systemadministratör och göra anspråk på en tillgänglig domän via Adobe Admin Console innan du migrerar användare. Läs mer <a href="https://helpx.adobe.com/se/enterprise/help/identity.html"> här</a>. </p> <p>Om du inte vill göra anspråk på domäner för Enterprise ID eller Federated ID hoppar du över det här steget och migrerar användare som Adobe ID:n. Läs mer om ID-typerna <a href="https://helpx.adobe.com/se/enterprise/help/identity.html"> här</a>. </p> </td> 
</tr> 
</tbody> 
</table>

1. Leta reda på domänen som innehåller de användar-ID som du vill migrera och klicka sedan på **[!UICONTROL Requiring Migration]** under **[!UICONTROL Select Users]**.
1. På sidan [!DNL Users] väljer du de användare som du vill migrera och klickar sedan på **[!UICONTROL Migrate]**.

   När du klickar på **[!UICONTROL Migrate]** får användarna en inbjudan (migreringen initierad) och måste acceptera den. Den här åtgärden flyttar användar-ID:t till migreringen slutförd. Du kan sedan inaktivera deras tidigare åtkomst till `[!DNL my.omniture.com].`

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. Ange vilken typ av ID du vill migrera användarna (Adobe ID eller Enterprise ID)

   När du har migrerat användare ändras statusen under kolumnmigreringsstatusen från *`Not Initiated`* till *`Migrated`*.

   Om *`Failed`* visas håller du pekaren över ikonen för att få en beskrivning av varför migreringen misslyckades.
