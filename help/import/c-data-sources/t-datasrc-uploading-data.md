---
description: Steg som beskriver hur du överför en datakällfil.
subtopic: Data sources
title: Överför en datakällfil
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Överför en datakällfil

Steg som beskriver hur du överför en datakällfil.

När du har förberett en datakälldatafil skickar du den till datakällor för bearbetning. Adobe har flera FTP-servrar för datakällor där du kan överföra datakällfiler. Tänk på följande om FTP-servrarna för datakällor:

* Välj FTP-information bredvid posten Datakälla på [!UICONTROL Data Sources Manage] fliken om du vill visa FTP-värd-, inloggnings- och lösenordsinformation för datakällans FTP-konto. Alla som har tillgång till den här informationen kan överföra data till rapportsviten.
* Av säkerhetsskäl stängs FTP-konton efter 30 dagars inaktivitet.
* FTP-konton är datakällsspecifika. Du kan inte använda ett FTP-konto för att överföra datakällfiler till flera datakällor.

**Så här överför du en datakällfil**

1. Använd en FTP-klient för att skicka data till din FTP-plats för datakällor.

   (Tillgängligt i länken FTP-information i Datakällshanteraren).

1. Överför en [!DNL .fin] fil för att meddela Adobe att överföringen av datakällfilen är slutförd.

   Filen måste ha exakt samma namn som [!DNL .fin] datakällfilen, förutom filtillägget. Adobe placerar inte datakällfilen i kö för bearbetning förrän du överför [!DNL .fin] filen.

   Överför inte filen förrän alla datakällfiler har överförts. Annars kan datakällor försöka bearbeta en ofullständig fil.
1. Håll utkik efter meddelanden under bearbetningen av datakällor.

   Hanteraren för datakällor visar eventuella fel som inträffar under filbearbetningen.

