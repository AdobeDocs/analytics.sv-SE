---
description: FTP-principen i Adobe inaktiverar automatiskt åtkomst till FTP-konton som är inaktiva i 90 dagar i följd.
keywords: ftp;sftp
title: Ta bort FTP-data och FTP-konton
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Ta bort FTP-data och FTP-konton

FTP-principen i Adobe inaktiverar automatiskt åtkomst till FTP-konton som är inaktiva i 90 dagar i följd.

Adobe tar sedan bort inaktiverade FTP-konton (och tar permanent bort alla data som lagras i dessa konton) efter ytterligare 90 dagars respitperiod. Ett FTP-konto som till exempel är inaktivt i 90 dagar (från 5 juli 2012 till 2 oktober 2012) inaktiveras 3 oktober 2012. Den tas sedan bort helt den 2 januari 2013.

Inga konton inaktiveras före 5 oktober 2012 och inga konton tas bort före 2 januari 2013.

Adobe tar också permanent bort gamla data i aktiva konton om dessa data inte har använts på 90 dagar.

Dessa regler gäller för alla FTP-konton som flyttas fram från och med den 5 juli 2012.

För att hjälpa oss i den här processen och för att säkerställa den förbättrade FTP-miljön fortsätter att tillhandahålla säker och tillförlitlig dataöverföring för våra kunder ber vi våra kunder att göra följande:

* Ta bort utgående data från FTP-systemet när dessa data har överförts till den interna miljön. Adobe identifierar och tar bort filer som finns kvar i systemet efter 90 dagar.
* Meddela Adobe när FTP-konton inte längre behövs så att de kan inaktiveras och tas bort.
