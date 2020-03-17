---
description: SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert bevara dina data.
keywords: ftp;sftp
title: Secure File Transfer Protocol - översikt
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Secure File Transfer Protocol - översikt

SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert bevara dina data.

## Push-leverans {#section_A47831BB1DCA490BB57F0940617AA506}

Det innebär att Adobes servrar&quot;skickar&quot; filen till dina servrar. I grund och botten levererar vi det till din slutpunkt.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) och [Analytics Data Feed](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) kan överföra data via SFTP.

Följande analysverktyg **kan inte** skicka data via SFTP:

* Rapporter och analyser
* Ad hoc-analys
* Report Builder

## Pull Delivery {#section_FA29FAEF02FE40B8B32452146A036F48}

Det innebär att filen skickas till någon av Adobes servrar med vanlig FTP. Om du vill ha filen på din server måste du ta bort den från Adobes server med hjälp av SFTP från servern till Adobes FTP-server. Du kan göra detta på något av följande tre sätt:

* [Anslut till Adobe via SFTP utan lösenord.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Anslut till ett Adobe FTP-konto med SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Du kan skicka alla rapporter du vill till Adobes FTP-liknande dataflöden/R&amp;A/Ad Hoc och så vidare och sedan dra av dem. Adobe kan inte leverera dessa rapporter till den SFTP-server som du har konfigurerat.

