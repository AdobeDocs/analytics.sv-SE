---
description: Aktiv FTP kontra passiv FTP styr hur portanslutningarna är upprättade och valet har vissa konsekvenser för brandväggen.
keywords: ftp;sftp
title: Använda passivt FTP-läge
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 7%

---

# Använda passivt FTP-läge

Aktiv FTP kontra passiv FTP styr hur portanslutningarna är upprättade och valet har vissa konsekvenser för brandväggen.

Adobe använder passiv FTP, som är en säkrare form av dataöverföring, där dataflödet ställs in och initieras av FTP-klienten (File Transfer Program) i stället för av FTP-serverprogrammet. Om du har problem med att ansluta till Adobe FTP kontrollerar du att du använder passivt läge.
