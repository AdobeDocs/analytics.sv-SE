---
description: Aktiv FTP kontra passiv FTP styr hur portanslutningarna är upprättade och valet har vissa konsekvenser för brandväggen.
keywords: ftp;sftp
title: Använda passivt FTP-läge
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 8%

---

# Använda passivt FTP-läge

Aktiv FTP kontra passiv FTP styr hur portanslutningarna är upprättade och valet har vissa konsekvenser för brandväggen.

Adobe använder passiv FTP, som är en säkrare form av dataöverföring, där dataflödet ställs in och initieras av FTP-klienten (File Transfer Program) i stället för av FTP-serverprogrammet. Om du har problem med att ansluta till Adobe FTP måste du använda passivt läge.
