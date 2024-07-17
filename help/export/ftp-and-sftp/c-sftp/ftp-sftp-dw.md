---
description: Adobe stöder export av begäranden om Data Warehouse till SFTP-servrar.
keywords: ftp;sftp
title: Skicka begäranden om Data Warehouse till SFTP-servrar
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Skicka begäranden om Data Warehouse till SFTP-servrar

Adobe stöder export av begäranden om Data Warehouse till SFTP-servrar, vilket beskrivs i [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) i artikeln [Konfigurera ett rapportmål för en begäran om Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Se till att följande uppgifter är slutförda:

* Endast port 22 används när en Data Warehouse begärs.
* Adobe `authorized_keys` finns i katalogen `.ssh` i rotkatalogen för den användare du loggar in med.
* Målet är inte `ftp.omniture.com`. SFTP-protokoll mellan Adobe interna servrar stöds inte.
* Målet stöder enfaktorsautentisering (PKI). Om det finns en tvåfaktorskontroll misslyckas leveransen av rapporten. Kontrollera att servern inte är konfigurerad att försöka utföra tvåfaktorsautentisering. Adobe Analytics kräver att bara nyckeln och inget annat används för att logga in.
* Adobe stöder SSHv2-kryptering och återgår till SSHv1 (endast RSA-nyckeln).

Så här skickar du en begäran om Data Warehouse via SFTP:

1. Slutför stegen som beskrivs i [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) i artikeln [Konfigurera ett rapportmål för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), inklusive hämtning av den offentliga nyckeln.
1. Logga in på SFTP-webbplatsen med samma inloggningsuppgifter som används för Datan Warehouse.
1. I rotkatalogen navigerar du till mappen `.ssh` (om det inte finns någon) och placerar `authorized_keys`-filen där.

1. Slutför begäran om Data Warehouse om du inte redan har gjort det, vilket beskrivs i [Konfigurera ett rapportmål för en Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
