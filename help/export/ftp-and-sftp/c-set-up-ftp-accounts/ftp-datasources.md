---
description: Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offlinedata eller historiska data till Experience Cloud.
keywords: ftp;sftp
title: Översikt över datakällor
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 7dc97ad5225baf56c829efc8c21b07154bdd8ff9
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# FTP-baserade datakällor

Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offlinedata eller historiska data till Experience Cloud.

När du har skapat en instans av Datakällor får du en FTP-plats som du kan använda för att överföra datakällfiler. När datakällorna har överförts hittas och bearbetas de automatiskt av datakällor. När filerna har bearbetats är dessa data tillgängliga för analysrapportering.

På fliken [!UICONTROL Create] i Datakällshanteraren kan du konfigurera en ny datakällinstans för den valda rapportsviten. [!UICONTROL Data Sources Wizard] vägleder dig genom processen att skapa en mall för datakällor och skapar en FTP-plats för överföring av data.

Leta reda på datakällan i fönstret [!UICONTROL Manage Data Sources] och välj länken FTP-information. FTP-inloggningsinformationen visas i fönstret [!UICONTROL Activate a Data Source] i avsnittet [!UICONTROL Upload/FTP Information].

Mer information om FTP-begränsningar och datalagring finns i [FTP-begränsningar och datalagring](/help/export/ftp-and-sftp/ftp-limits.md).

## Om FIN-filen för överföring av klassificeringar och datakällor {#section_1484719F8A134EAE91212DBD8F15174F}

När du överför en klassificering eller [!UICONTROL Data Source] fil ( [!DNL .tab] eller [!DNL .txt]) kräver överföringen också att du överför en tom fil med exakt samma namn som den datafil som importeras, men med filnamnstillägget [!DNL .fin]. Den här [!DNL .fin]-filen är en färdig fil. Syftet med filen är att tala om för systemet att datafilen har överförts helt till FTP-kontot. Med filen [!DNL .fin] kan Adobe känna igen att du är klar med importen. När du har skickat den tar Adobe bort båda filerna från FTP-filen och börjar bearbeta importen.
Importfil: [!DNL Classifications.tab]

Slutför fil: [!DNL Classifications.fin]

Om du överför dina datakällor eller SAINT-filer utan någon tillhörande [!DNL .fin]-fil, lägger Adobe inte till den i kön för bearbetning. Filen finns kvar på FTP och används inte på dina data i [!UICONTROL Experience Cloud]. Du meddelas bara om du har angett din e-postadress som [!UICONTROL Notification Recipient] i rapportfönstret i [!UICONTROL Create FTP Account]. Om ingen e-postadress anges i det här fältet skickas inget meddelande.

Om du överför filen med en [!DNL .fin]-fil, men det finns ett fel i filen, skickas den för bearbetning, men felet gör att bearbetningen avbryts och filen skickas till en felmapp. Om detta inträffar skickas ett meddelande till den e-postadress som visas i fältet [!UICONTROL Notification Recipient] i fönstret [!UICONTROL Create FTP Account]. Om ingen e-postadress anges skickas inget meddelande.
