---
description: Konfigurera och använd FTP-konton som ligger i Adobe.
keywords: ftp;sftp
title: Konfigurera FTP-konton - översikt
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Konfigurera FTP-konton - översikt

Konfigurera och använd FTP-konton som ligger i Adobe.

Adobe har högpresterande FTP-kluster med hög tillgänglighet som är särskilt utformade för att förbättra tillförlitligheten i filöverföringen, samtidigt som de ger höga prestanda.

Adobe-kunder får underhållsmeddelanden via sin standardprocess eftersom underhållshändelser schemaläggs. För att säkerställa att FTP-systemen i Adobe fungerar som de är konstruerade och fortsätter att tillhandahålla säker och tillförlitlig dataöverföring med höga prestanda, begär Adobe att följande riktlinjer ska följas:

* De flesta FTP-konton (klassificeringar, datakällor och andra) för Adobe aktiveras automatiskt när den angivna funktionen konfigureras. För Data Feed- och General file delivery-konton kan Adobe Customer Care skapa ett nytt FTP-konto åt dig. Den här processen används för att säkerställa både säkerhet och tillgängligt utrymme för FTP-kontot.
* Användare bör ta bort data som levereras av Adobe till FTP-kontot efter att data har överförts till deras system.
* Meddela Adobe när FTP-konton inte längre behövs så att de kan inaktiveras.

FTP-värdnamnet för Adobe är `ftp://ftp.omniture.com` eller `ftp://ftp2.omniture.com`.

Den här informationen, tillsammans med ett användarnamn och lösenord, ska tillhandahållas antingen i [!UICONTROL Experience Cloud] (för klassificeringar och datakällor) eller av Adobe som ansvarar för att konfigurera kontot på din begäran. Om du inte vet vilken FTP-adress du ska använda kontaktar du kontoteamet på Adobe som kan ange rätt adress. För klassificeringar och konton för datakällor har Adobe inte heller någon specifik tid på dagen som FTP-filer bearbetas. I stället använder Adobe ett skript som hela tiden avfrågar FTP-konton för nya filprocesser. Filer som överförs till dessa konton bearbetas så snabbt som möjligt.
