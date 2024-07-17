---
description: SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert behålla dina data.
keywords: ftp;sftp
title: Secure File Transfer Protocol - översikt
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Secure File Transfer Protocol - översikt

SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert behålla dina data.

## Push-leverans {#section_A47831BB1DCA490BB57F0940617AA506}

Det innebär att Adobe-servrar&quot;skickar&quot; filen till dina servrar. I grund och botten levererar vi det till din slutpunkt.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) och [Analysdatafeed](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) kan skicka data via SFTP.

Report Builder **kan inte** skicka data via SFTP.

## Pull Delivery {#section_FA29FAEF02FE40B8B32452146A036F48}

Det innebär att filen skickas till en av Adobe servrar med vanlig FTP. Om du vill ha filen på servern måste du ta bort den från Adobe-servern med hjälp av SFTP från servern till Adobe FTP-servern. Du kan göra detta på något av följande tre sätt:

* [Anslut till Adobe via SFTP utan lösenord.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Anslut till ett Adobe FTP-konto med SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Du kan skicka alla rapporter som du vill ha till Adobe FTP-liknande dataflöden/R&amp;A/Ad Hoc och så vidare och sedan ta bort dem. Adobe kan inte leverera dessa rapporter till den SFTP-server som du har konfigurerat.
