---
description: Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offline- eller historiska data till Experience Cloud.
keywords: ftp;sftp
title: Datakällor
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Datakällor

Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offline- eller historiska data till Experience Cloud.

När du har skapat en instans av Datakällor får du en FTP-plats som du kan använda för att överföra datakällfiler. När datakällorna har överförts hittas och bearbetas de automatiskt av datakällor. När filerna har bearbetats är dessa data tillgängliga för analysrapportering.

På fliken [!UICONTROL Create] i Datakällshanteraren kan du konfigurera en ny instans av Datakällor för den valda rapportsviten. I guiden får du hjälp med att skapa en mall för datakällor och skapar en FTP-plats för överföring av data. [!UICONTROL Data Sources Wizard]

Leta reda på datakällan och välj länken FTP-information i [!UICONTROL Manage Data Sources] fönstret. FTP-inloggningsinformationen visas i [!UICONTROL Activate a Data Source] fönstret i [!UICONTROL Upload/FTP Information] avsnittet.

Mer information om FTP-begränsningar och datalagring finns i [FTP-gränser och datalagring](/help/export/ftp-and-sftp/ftp-limits.md).

## Om FIN-filen för överföring av klassificeringar och datakällor {#section_1484719F8A134EAE91212DBD8F15174F}

När du överför en klassificering eller [!UICONTROL Data Source] fil ( [!DNL .tab] eller [!DNL .txt]) kräver överföringen även att du överför en tom fil med exakt samma namn som den datafil som importeras, men med ett [!DNL .fin] tillägg. Den här [!DNL .fin] filen är en färdig fil. Syftet med filen är att tala om för systemet att datafilen har överförts helt till FTP-kontot. Filen gör att Adobe kan känna igen att du är klar med importen. [!DNL .fin] När du har skickat den tar Adobe bort båda filerna från FTP-filen och börjar bearbeta importen.
Importera fil: [!DNL Classifications.tab]

Slutfil: [!DNL Classifications.fin]

Om du överför dina datakällor eller SAINT-filer utan någon tillhörande [!DNL .fin] fil, läggs de inte till i kön för bearbetning. Filen finns kvar på FTP och används inte på dina data i [!UICONTROL Experience Cloud]. Du meddelas bara om du har angett din e-postadress som [!UICONTROL Notification Recipient] referens i [!UICONTROL Create FTP Account] rapportfönstret. Om ingen e-postadress anges i det här fältet skickas inget meddelande.

Om du överför filen med en [!DNL .fin] fil, men det finns ett fel i filen, skickas den för bearbetning, men felet gör att bearbetningen avbryts och filen skickas till en felmapp. Om detta inträffar skickas ett meddelande till den e-postadress som visas i [!UICONTROL Notification Recipient] fältet i [!UICONTROL Create FTP Account] fönstret. Om ingen e-postadress anges skickas inget meddelande.
