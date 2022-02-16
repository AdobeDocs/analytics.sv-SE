---
description: Det går bara att ansluta utan lösenord till FTP-konton med både en SFTP-anslutning och en alternativ autentiseringsmetod. Detta inbegriper en uppsättning med två filer (en som finns på FTP-kontot och den andra som finns på datorn) som kallas för en kombination av offentlig och privat nyckel.
keywords: ftp;sftp
title: Ansluta till Adobe via SFTP utan lösenord
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 2%

---

# Ansluta till Adobe via SFTP utan lösenord

Det går bara att ansluta utan lösenord till FTP-konton med både en SFTP-anslutning och en alternativ autentiseringsmetod. Detta inbegriper en uppsättning med två filer (en som finns på FTP-kontot och den andra som finns på datorn) som kallas för en kombination av offentlig och privat nyckel.

Detta är inte mindre säkert än lösenordsautentisering. Det är en annan form av autentisering som inte kräver att användaren skriver in ett lösenord varje gång. När de används på rätt sätt kan den aktuella datorn logga in utan att behöva ange ett lösenord. Detta måste göras dator för dator. Alla andra anslutningar som inte använder dessa nyckelfiler måste ange ett lösenord.

En del klienter kräver en SFTP (Secure File Transfer Protocol) för överföring av känsliga data. En SFTP-anslutning är säkrare än en vanlig FTP-anslutning eftersom den tillåter krypterad datakommunikation. Som standard är alla FTP-konton i Adobe redo för SFTP. En SFTP-anslutning kan öppnas med ett giltigt användarnamn och lösenord med hjälp av en SFTP-klient som ansluter till port 22 (vanliga FTP-anslutningar som inte är säkra använder port 21).

När du använder SFTP är det möjligt att, under särskilda förhållanden, använda privata nycklar för att ansluta till kontot utan lösenord. Med den här metoden kan datorn använda nyckelfiler för autentisering i stället för vanlig lösenordsautentisering. Det innebär att det endast är den dator som har den privata nyckeln som kan ansluta utan ett lösenord. Alla andra datorer/användare måste fortfarande använda lösenordsautentisering (såvida inte privata nycklar har ställts in på dessa andra datorer också).

**Så här konfigurerar och använder du privata nycklar för lösenordslös autentisering**

1. Ett FTP-konto har skapats (Adobe).

   En Adobe-representant kan skapa ett FTP-konto om det inte redan finns ett. Kontakta din kontoansvarige på Adobe eller Adobe kundtjänst om du vill skapa ett konto.
1. Skapa offentlig/privat nyckel (kund).

   Skapa en kombination av offentlig och privat nyckel. Den privata nyckeln är en fil som är privat för datorn/servern och som finns där. Den offentliga nyckelfilen måste överföras till Adobe-kontot. När det används på det här sättet kan du ansluta utan lösenordsautentisering. Den offentliga nyckelfilen i Adobe matchar den privata nyckelfilen på datorn/servern och autentiseras på det sättet.

   Om du vill skapa de här filerna måste du engagera din interna nätverkssupportgrupp och skapa en nyckeluppsättning som passar just din miljö. Det finns många verktyg och program som kan användas för att skapa dessa två filer.

   Ett exempel på hur detta kan göras i en UNIX-skalmiljö visas nedan. Detta är bara ett exempel på hur detta kan göras och fungerar som en bra referenspunkt för att kommunicera krav till ditt team eller din interna nätverksgrupp.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Överför offentlig nyckel till FTP-konto (kund).

   Överför och testa den offentliga nyckeln. Anslut till FTP-kontot i Adobe och skapa en [!DNL .ssh] om den inte redan finns. Överför [!DNL authorized_keys] till denna [!DNL .ssh] katalog. Detta kan göras på många olika sätt (kommandorad, grafisk FTP-klient och så vidare). Allt som krävs är möjligheten att skapa en katalog och överföra en fil.

   Här är ett exempel på hur man gör detta med ett UNIX-skal.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
