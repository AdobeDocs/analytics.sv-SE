---
description: Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offlinedata eller historiska data till Experience Cloud.
keywords: ftp;sftp
title: Datakällor
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Datakällor

Ni kan använda Analytics för att skapa och hantera FTP-baserade datakällor, som utnyttjar FTP-filöverföring för att importera offlinedata eller historiska data till Experience Cloud.

När du har skapat en instans av Datakällor får du en FTP-plats som du kan använda för att överföra datakällfiler. När datakällorna har överförts hittas och bearbetas de automatiskt av datakällor. När filerna har bearbetats är dessa data tillgängliga för analysrapportering.

The [!UICONTROL Create] I Data Sources Manager kan du konfigurera en ny instans av Datakällor för den valda rapportsviten. The [!UICONTROL Data Sources Wizard] hjälper dig genom processen att skapa en mall för datakällor och skapar en FTP-plats för överföring av data.

I [!UICONTROL Manage Data Sources] söker du efter datakällan och väljer länken FTP-information. FTP-inloggningsinformationen visas i [!UICONTROL Activate a Data Source] i [!UICONTROL Upload/FTP Information] -avsnitt.

Mer information om FTP-begränsningar och datalagring finns i [FTP-begränsningar och datalagring](/help/export/ftp-and-sftp/ftp-limits.md).

## Om FIN-filen för överföring av klassificeringar och datakällor {#section_1484719F8A134EAE91212DBD8F15174F}

När du överför en klassificering eller [!UICONTROL Data Source] fil ( [!DNL .tab] eller [!DNL .txt]) kräver överföringen också att du överför en tom fil med exakt samma namn som den datafil som importeras, men med en [!DNL .fin] tillägg. Detta [!DNL .fin] filen är en färdig fil. Syftet med filen är att tala om för systemet att datafilen har överförts helt till FTP-kontot. The [!DNL .fin] kan Adobe känna igen att du är klar med importen. När du har skickat den tar Adobe bort båda filerna från FTP-filen och börjar bearbeta importen.
Importera fil: [!DNL Classifications.tab]

Slutfil: [!DNL Classifications.fin]

Om du överför dina datakällor eller SAINT-filer utan att ha någon medföljande fil [!DNL .fin] filen, Adobe lägger inte till den i kön för bearbetning. Filen finns kvar på FTP och används inte på dina data i [!UICONTROL Experience Cloud]. Du meddelas bara om du har angett din e-postadress som [!UICONTROL Notification Recipient] i [!UICONTROL Create FTP Account] rapportfönstret. Om ingen e-postadress anges i det här fältet skickas inget meddelande.

Om du överför filen med en [!DNL .fin] -filen, men det finns ett fel i filen, som skickas för bearbetning, men felet gör att bearbetningen avbryts och filen skickas till en felmapp. Om detta inträffar skickas ett meddelande till den e-postadress som anges i [!UICONTROL Notification Recipient] i [!UICONTROL Create FTP Account] -fönstret. Om ingen e-postadress anges skickas inget meddelande.
