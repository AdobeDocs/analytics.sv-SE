---
title: Uppgradering av SFTP-tjänster - frågor och svar
description: Frågor och svar om den planerade uppgraderingen av SFTP-tjänster.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Uppgradering av SFTP-tjänster - frågor och svar

20 september 2022 kommer Adobe Analytics att uppgradera sitt säkra filöverföringsprotokoll [SFTP] tjänster för bättre säkerhet vid filöverföringar. Den här ändringen innebär att vissa SFTP-klientkonfigurationer inte längre stöds. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de ändringar som beskrivs nedan.

## Hur kan jag avgöra vilka algoritmer, anslutningstyper och protokoll som används av min organisation just nu?

De FTP/SFTP-program du använder bör ange vilka specifika inställningar som används i de anslutningar du har konfigurerat för datautbyte med Adobe Analytics. Programmet bör även innehålla dokumentation om de olika alternativ som är tillgängliga för anslutningar. De alternativ som kommer att stödjas efter den här uppdateringen stöds och accepteras allmänt i branschen.

De anslutningsalternativ som tas bort anses i allmänhet vara föråldrade och används inte i den aktuella programvaran. Om du har uppgraderat FTP/SFTP-programmet under de senaste tre åren har du troligen redan en kompatibel anslutning.

## Vilka Adobe Analytics-funktioner använder SFTP för datainmatning?

Följande funktioner erbjuder ett alternativ för att överföra data till Adobe Analytics med SFTP.

* [Klassificeringar](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html)

* [Datafeeds](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Datakällor](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Levererade Data Warehouse-rapporter](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* Dessutom har vissa anpassade implementeringar skapats via [Ingenjörstjänster](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) kan använda SFTP för att utbyta data med Adobe.

## Vilka specifika ändringar kommer att ingå i den här uppdateringen?

Nedan finns en detaljerad lista över vilka anslutningar och algoritmer som kommer att tas bort och vilka som kommer att stödjas:

* SFTP-protokollets mac-algoritmer:

   * Vi kommer inte längre att stödja: mac-md5, mac-md5-96, mac-ripemd160, hmacripemd160@openssh.com, mac-sha1, mac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Vi kommer endast att stödja: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, mac-sha2-512, macsha2-256, umac-128@openssh.com

* SFTP-protokollets ciphers-algoritm:

   * Vi kommer inte längre att stödja: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Vi stöder bara: aes128-ctr, aes192-ctr, aes256-ctr

* Anslutningar som stöds av SFTP-protokoll:

   * Vi kommer inte längre att ha stöd för att använda kommandon eller anslutningar för scp och rsync via SFTP-protokollet

   * Vi stöder bara rena SFTP-protokollanslutningar

* FTP/SFTP-klienter/protokoll stöds:

   * FTP: vsftpd version 3.0.2-25 eller senare

   * SFTP: öppen version 7.4p1-21 eller senare
