---
description: Instruktioner för att konfigurera säker överföring med FTP-servrar i Adobe.
keywords: ftp;sftp
title: Ansluta till ett Adobe FTP-konto med SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 11%

---

# Ansluta till ett Adobe FTP-konto med SFTP

Instruktioner för att konfigurera säker överföring med FTP-servrar i Adobe.

1. Begär ett FTP-värdkonto på Adobe (50 MB-kvot).
1. Skapa offentliga/privata RSA-nycklar. Kör i Linux:

   ```
   ssh-keygen -t rsa
   ```

   Om du arbetar i en Windows-miljö använder du puttyGen för att skapa nycklarna.

1. Skapa en fil med namnet [!DNL authorized_keys] (inget tillägg).
1. Kopiera innehållet i den offentliga nyckeln till [!DNL authorized_keys].
1. Överför [!DNL authorized_keys] till ett FTP-konto:

   * Anslut till Adobe FTP-kontot.
   * Skapa en [!DNL .ssh] katalog (om den inte redan finns).
   * Överför [!DNL authorized_keys] till [!DNL .ssh] katalog.

1. Testa anslutningen genom att logga in på FTP-kontot med SFTP.

Mer detaljerad information finns i [Ansluta till Adobe via sFTP utan lösenord_..](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
