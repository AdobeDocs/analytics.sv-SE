---
description: Instruktioner för säker överföring med Adobes FTP-servrar.
keywords: ftp;sftp
title: Anslut till ett Adobe FTP-konto med SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Anslut till ett Adobe FTP-konto med SFTP

Instruktioner för säker överföring med Adobes FTP-servrar.

1. Begär ett FTP-värdkonto hos Adobe (kvot på 50 MB).
1. Skapa offentliga/privata RSA-nycklar. Kör i Linux:

   ```
   ssh-keygen -t rsa
   ```

   Om du arbetar i en Windows-miljö använder du puttyGen för att skapa nycklarna.

1. Skapa en fil med namnet [!DNL authorized_keys] (inget tillägg).
1. Kopiera innehållet i den publika nyckeln till [!DNL authorized_keys].
1. Överför [!DNL authorized_keys] till ett FTP-konto:

   * Anslut till Adobe FTP-kontot.
   * Skapa en [!DNL .ssh] katalog (om den inte redan finns).
   * Överför [!DNL authorized_keys] filen till [!DNL .ssh] katalogen.

1. Testa anslutningen genom att logga in på FTP-kontot med SFTP.

Mer information finns i [Ansluta till Adobe via sFTP utan lösenord_..](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
