---
description: Så här migrerar du Analytics-användarkonton som Enterprise ID eller Federated ID till Adobe Admin Console.
title: Migrera Analytics-användarkonton för Enterprise ID och Federated ID
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# Migrera Analytics-användarkonton för Enterprise ID och Federated ID

Så här migrerar du Analytics-användarkonton som Enterprise ID eller Federated ID till Adobe Admin Console.

## Förutsättningar {#prereqs}

Krav för att hantera användare i Adobe Admin Console.

För nya domäner och kataloger följer du stegen för att:

* Konfigurera en katalog
* Konfigurera domäner
* Länka domäner till kataloger

Se [Konfigurera ett identitetssystem](https://helpx.adobe.com/enterprise/using/set-up-identity.html) om du behöver hjälp.

Om en katalog redan har skapats i en annan organisation av en annan affärsenhet eller grupp följer du stegen i [katalogförvaltning](https://helpx.adobe.com/enterprise/using/set-up-identity.html#Directorytrusting) för att skapa katalogen i organisationen som du använder för Analytics.

## Migrera användarkonton för Enterprise ID och Federated ID {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

I den här proceduren kommer du att:

* Hämta en inloggningslista från **[!UICONTROL Analytics]** > **[!UICONTROL Analytics Users & Assets]**.

* Hämta en aktuell användarlista från **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**.

* Jämför listorna (söker efter dubbletter så att du inte skriver över kontodata i Adobe Admin Console).
* Överför en slutförd [!DNL .csv] (från **[!UICONTROL Admin Console]** > **[!UICONTROL Users]**) med Enterprise ID- eller Federated ID-användare till Adobe Admin Console.

Om du behöver migrera befintliga Adobe ID-användarkonton till ett Enterprise ID eller Federated ID kontaktar du Adobe kundtjänst och begär en [bulkanvändaridentitetsväxling](https://helpx.adobe.com/enterprise/using/bulk-operations.html).

**Migrera användarkonton**

1. Hämta Analytics-användarinloggningsfilen ( [!DNL User Logins List.tab]) från Analytics User Management, med någon av följande metoder (beroende på om du redan har migrerat användare).
   1. *Före migreringen,* navigera till **[!UICONTROL Admin]** > **[!UICONTROL User Management (Legacy)]** > **[!UICONTROL Edit Users]** och sedan klicka **[!UICONTROL Download Report]**.

      ![](/help/admin/admin/user-management2/user-migration/assets/download-report.png)

      Länken Hämta rapport visas endast för kunder som inte har migrerat användare.

   1. *Om du redan har migrerat användare* navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Analytics users and Assets]**.

      ![Steginformation](/help/admin/admin/user-management2/user-migration/assets/admin-analytics-users-assets.png)

   1. På [!DNL Users] sida, markera användare och klicka sedan på **[!UICONTROL Export to CSV]**.

      ![Steginformation](/help/admin/admin/user-management2/user-migration/assets/export-csv-migrate.png)

   1. Öppna den hämtade filen [!DNL User List.csv] i Excel.

      Var beredd att kopiera *`Email`*, *`First Name`* och *`Last Name`* värden till [!DNL sample.csv] -fil (beskrivs i nästa steg).

      >[!IMPORTANT]
      >
      >Värdena i CSV-filen måste vara kommaavgränsade.

      >[!TIP]
      >
      >Under det här steget rekommenderar Adobe att du effektiviserar användarlistan så att endast de användare som har ett giltigt e-post-ID inkluderas i Enterprise- eller Federated ID-migreringen.

1. I [!UICONTROL Admin Console], ladda ned en lista över Adobe Admin Console-användare:

   1. Navigera till [!UICONTROL Admin Console] > **[!UICONTROL Users]** och sedan klicka [Exportera användarlistan till CSV](https://helpx.adobe.com/enterprise/using/users.html).

      ![](/help/admin/admin/user-management2/user-migration/assets/export-csv.png)

   1. Jämför de två filerna: de befintliga Adobe Admin Console-användarna i den exporterade [!DNL .csv] fil ( [!DNL sample.csv], i det här exemplet) med användarna i Analytics [!DNL User Logins List.csv] -fil.

      >[!IMPORTANT]
      >
      >Ta bort dubbletter från Analytics [!DNL User Logins List.csv] -fil. Det här steget förhindrar att befintliga användarbehörigheter för Experience Cloud skrivs över i Adobe Admin Console och ger dig en lista över konton som ska migreras.

1. Hämta CSV-mallen från Adobe Admin Console:
   1. Klicka på fliken Användare **[!UICONTROL Add users by CSV]** sedan **[!UICONTROL Download CSV Template]**.

      ![Steginformation](/help/admin/admin/user-management2/user-migration/assets/add-users-csv.png)

   1. Välj **[!UICONTROL Standard Template]**.

      Det här steget hämtar en [!DNL sample.csv] mallfil.

      ![](/help/admin/admin/user-management2/user-migration/assets/download-csv-template.png)

1. Kopiera *`Email`*, *`First Name`* och *`Last Name`* kolumnvärden från [!DNL User Logins List.tab] till motsvarande kolumner i [!DNL sample.csv] mall.

   **Exempel på mallfil**

   ![](/help/admin/admin/user-management2/user-migration/assets/sample.png)

1. I mallen ( [!DNL sample.csv]) fyller du i följande obligatoriska fält:

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>E-post </p> </td> 
   <td colname="col2"> <p>Kopierad från <span class="filepath"> Användarens inloggningslista.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Förnamn </p> </td> 
   <td colname="col2"> <p>Kopierad från <span class="filepath"> Användarens inloggningslista.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Efternamn </p> </td> 
   <td colname="col2"> <p>Kopierad från <span class="filepath"> Användarens inloggningslista.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identitetstyp </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> eller <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domän </p> </td> 
   <td colname="col2"> <p>Se till att domäner i <span class="term"> Domän</span> och <span class="term"> E-post</span> -kolumnen matchar de domäner som har upprättats i förutsättningarna</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Landskod </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Mer information om fälten i [!DNL .csv] -fil, se [CSV-filformat](https://helpx.adobe.com/enterprise/using/users.html).

>[!NOTE]
>
>Andra kolumner, till exempel [!UICONTROL Product Configurations] och [!UICONTROL Admin Roles] kan vara tom.

1. Överför mallfilen på fliken Användare i Adobe Admin Console genom att klicka på **[!UICONTROL Add users by CSV]** (enligt steg 3.).
1. Kör migreringsverktyget i Analytics (enligt beskrivningen i [Migrera användarkonton för Analytics](/help/admin/admin/user-management2/user-migration/t-migrate-users.md).
1. Klicka **[!UICONTROL Migrate]** > **[!UICONTROL Migrate as Enterprise IDs]**.

   ![Steginformation](/help/admin/admin/user-management2/user-migration/assets/migrate-as-enterprise.png)

   När du klickar **[!UICONTROL Migrate]**, är användare länkade till Enterprise ID/Federated ID i Adobe Admin Console. Behörigheterna för det äldre användarkontot i Analytics matchar behörigheterna som ges till Enterprise/Federated ID-inloggningen **[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL Product Profiles]**. Användar-ID:t visas i migreringsknappen Slutförd. Du kan inaktivera deras äldre [!DNL my.omniture.com] åtkomst.

   Efter migrering av användare ändras statusen under kolumnen Migreringsstatus från **[!UICONTROL Not Initiated]** till **[!UICONTROL Migrated]**.

   Adobe ID-användare som visas i migreringsverktyget kan också migreras i den här processen. De måste fortfarande logga in med sin Adobe ID tills en identitetsväxling görs. Kontakta Adobe kundtjänst om du behöver hjälp med att byta identitet.
