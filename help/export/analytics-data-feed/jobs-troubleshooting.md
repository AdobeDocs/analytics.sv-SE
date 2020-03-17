---
description: Om ett fel inträffar rapporteras ett fel i kolumnen Jobbstatus.
keywords: Data Feed;job;troubleshooting;error;ftp;chdir;connect;login;put
title: Felsöka jobb
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Felsöka jobb

Om du har problem med att få en datafeed att visas på FTP-webbplatsen kan du använda den här sidan för att förstå varför.

## Felkoder

Om ett fel inträffar rapporteras ett fel i kolumnen Jobbstatus.

### FTP-chdir-fel

Feed kan inte navigera eller skriva till den angivna mappen. Kontrollera att målmappen finns på FTP-platsen och att de angivna inloggningsuppgifterna har rätt läs- och skrivbehörighet för den mappen.

### FTP-anslutningsfel

Feed kan inte ansluta till FTP-målet. Kontrollera att FTP-målet är korrekt och giltigt.

### FTP-fel

Ett allmänt fel där feed inte kan skriva filen till FTP-platsen. Det här felet kan bero på att FTP-serverns disk är full eller att kvoten har överskridits. Felet kan också bero på ett nätverks- eller målserverfel.

### FTP-inloggningsfel

Feed kan inte logga in med de angivna autentiseringsuppgifterna. Kontrollera att FTP-användarnamnet och -lösenordet är korrekta.

### FTP-Put-fel

Feed kan inte skriva filer till FTP-platsen. Kontrollera att FTP-inloggningen har rätt behörighet för att både läsa och skriva data på FTP-platsen. Det här felet kan även bero på en full disk eller en överskriden diskkvot på FTP-servern.

## Steg som ska felsökas

Logga in på FTP-platsen och överför filer till den. I de flesta fall kan du ange felpunkten genom att använda dessa steg.

1. Logga in på FTP-platsen med Utforskaren (Windows) eller Finder (Mac). Kontrollera att du använder FTP-protokoll (`ftp://`). Om du inte kan nå FTP-platsen kan du tillsammans med ägaren av FTP-platsen fastställa rätt mål.

   ![Utforskaren](assets/file_explorer.png)

2. Ett popup-fönster med en fråga om användarnamn och lösenord visas. Ange autentiseringsuppgifterna. Om inloggningsuppgifterna godkänns visas det aktuella innehållet på FTP-platsen i fönstret. Om inloggningsuppgifterna inte godkänns kan du samarbeta med FTP-ägaren för att kontrollera att användarnamnet och lösenordet är korrekta.
3. Överför en fil till FTP-platsen genom att dra den till det autentiserade fönstret. Alla bilder och textdokument är tillräckliga. Om du får ett fel när du försöker montera en fil på FTP-platsen bör du tillsammans med FTP-ägaren kontrollera att det finns tillräckligt med diskutrymme och att användarnamnet har skrivbehörighet för FTP-platsen.
4. När du har bekräftat att filen finns på FTP-platsen kan du ta bort filen som överfördes i föregående steg.
5. Om alla ovanstående steg fungerar och du ändå får ett FTP-fel ber du en kundsupportrepresentant att kontakta Kundtjänst.
