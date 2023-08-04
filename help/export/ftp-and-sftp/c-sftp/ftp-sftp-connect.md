---
description: Instruktioner för att konfigurera säker överföring med FTP-servrar i Adobe.
keywords: ftp;sftp
title: Ansluta till ett Adobe FTP-konto med SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 8%

---

# Ansluta till ett FTP-konto med SFTP

Så här ställer du in säker överföring med FTP:

1. (Villkorligt) Om du vill konfigurera säker överföring med FTP-servrar i Adobe:

   1. Begär ett FTP-värdkonto på Adobe (50 MB-kvot).

   1. Skapa offentliga/privata RSA-nycklar.

      * I Linux-miljön kör du:

        ```
        ssh-keygen -t rsa
        ```

      * I en Windows-miljö använder du puttyGen.

1. (Villkorligt) Om du vill konfigurera säker överföring med din egen FTP-plats måste du ha en SFTP-värd, ett användarnamn och målplatsen som innehåller en giltig offentlig RSA- eller DSA-nyckel. Du kan hämta lämplig offentlig nyckel när du skapar flödet.

1. Skapa en fil med namnet [!DNL authorized_keys] (inget tillägg).

1. Kopiera innehållet i den offentliga nyckeln till [!DNL authorized_keys].

1. Överför [!DNL authorized_keys] till ett FTP-konto:

   * Anslut till Adobe FTP-kontot.
   * Skapa en [!DNL .ssh] (om den inte redan finns).
   * Ladda upp [!DNL authorized_keys] till [!DNL .ssh] katalog.

1. Testa anslutningen genom att logga in på FTP-kontot med SFTP.

Mer detaljerad information finns i [Ansluta till Adobe via sFTP utan lösenord_..](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
