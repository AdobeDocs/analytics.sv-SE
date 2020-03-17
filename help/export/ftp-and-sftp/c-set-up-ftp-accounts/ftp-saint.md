---
description: Alternativet för klassificeringar (SAINT) FTP ger större flexibilitet vid överföring av stora klassificeringsdatauppsättningar, inklusive möjligheten att överföra data till flera rapportsviter och att överföra datauppsättningar som är större än 50 000 rader.
keywords: ftp;sftp
title: Klassificeringar
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Klassificeringar

Alternativet för klassificerings-FTP ger större flexibilitet vid överföring av stora klassificeringsdatauppsättningar, inklusive möjligheten att överföra data till flera rapportsviter och att överföra datauppsättningar som är större än 50 000 rader.

Se [klassificeringar](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) för steg om hur du hämtar klassificeringsdata via FTP och hur du överför datafiler via FTP (inklusive stegen för att skapa ett FTP-konto).

Hur lång tid det tar för systemet att importera dessa filer varierar beroende på ett antal faktorer. Om det fortfarande finns en överförd fil på FTP-servern efter sex timmar kontaktar du Adobes kundtjänst tillsammans med de användare i organisationen som stöds.

Vid en lyckad import visas omedelbart lämpliga ändringar i en export, medan dataändringarna i Analytics kan ta upp till fyra timmar med en webbläsarimport och upp till 24 timmar med en FTP-import.

Mer information om FTP-begränsningar och datalagring finns i [FTP-gränser och datalagring](/help/export/ftp-and-sftp/ftp-limits.md).

## Om FIN-filen för överföring av klassificeringar och datakällor {#section_1484719F8A134EAE91212DBD8F15174F}

När du överför en klassificering eller [!UICONTROL Data Source] fil ( [!DNL .tab]eller [!DNL .txt]) kräver överföringen även att du överför en tom fil med exakt samma namn som den datafil som importeras, men med ett [!DNL .fin] tillägg. Den här [!DNL .fin] filen är en färdig fil. Syftet med filen är att tala om för systemet att datafilen har överförts helt till FTP-kontot. Filen gör att Adobe kan känna igen att du är klar med importen. [!DNL .fin] När du har skickat den tar Adobe bort båda filerna från FTP-filen och börjar bearbeta importen.
Importera fil: [!DNL Classifications.tab]

Slutfil: [!DNL Classifications.fin]

Om du överför dina datakällor eller klassificeringsfiler utan någon tillhörande [!DNL .fin] fil läggs de inte till i kön för bearbetning. Filen finns kvar på FTP och används inte på dina data i [!UICONTROL Experience Cloud]. Du meddelas bara om du har angett din e-postadress som [!UICONTROL Notification Recipient] i Analytics- [!UICONTROL Create FTP Account] fönstret. Om ingen e-postadress anges i det här fältet skickas inget meddelande.

Om du överför filen med en [!DNL .fin] fil, men det finns ett fel i filen, skickas den för bearbetning, men felet gör att bearbetningen avbryts och filen skickas till en felmapp. Om detta inträffar skickas ett meddelande till den e-postadress som visas i [!UICONTROL Notification Recipient] fältet i [!UICONTROL Create FTP Account] fönstret. Om ingen e-postadress anges skickas inget meddelande.
