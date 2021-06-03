---
description: SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert behålla dina data.
keywords: ftp;sftp
title: Secure File Transfer Protocol – översikt
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 9%

---

# Secure File Transfer Protocol – översikt

SFTP är ett säkert protokoll för överföring av data som säkerställer att ingen kan se dina data utom du. Adobe Engineering Services kan skapa ett SFTP-konto för att säkert behålla dina data.

## Push-leverans {#section_A47831BB1DCA490BB57F0940617AA506}

Det innebär att Adobe-servrar&quot;skickar&quot; filen till dina servrar. I grund och botten levererar vi det till din slutpunkt.

[Data ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) Warehouseoch  [Analytics Data ](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) Feedkan överföra data via SFTP.

Följande analysverktyg **kan inte** skicka data via SFTP:

* Rapporter och analyser
* Ad Hoc Analysis
* Report Builder

## Pull Delivery {#section_FA29FAEF02FE40B8B32452146A036F48}

Det innebär att filen skickas till en av Adobe servrar med vanlig FTP. Om du vill ha filen på servern måste du ta bort den från Adobe-servern med hjälp av SFTP från servern till Adobe FTP-servern. Du kan göra detta på något av följande tre sätt:

* [Ansluta till Adobe via SFTP utan lösenord.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Anslut till ett Adobe FTP-konto med SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Du kan skicka alla rapporter som du vill ha till Adobe FTP-liknande dataflöden/R&amp;A/Ad Hoc och så vidare och sedan ta bort dem. Adobe kan inte leverera dessa rapporter till den SFTP-server som du har konfigurerat.
