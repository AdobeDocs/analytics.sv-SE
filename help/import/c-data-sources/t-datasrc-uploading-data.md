---
description: Steg som beskriver hur du överför en datakällfil.
subtopic: Data sources
title: Överföra en Data Sources-fil
topic-fix: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
exl-id: 8b7fa32c-01f2-452b-bf8e-8a81da266926
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 3%

---

# Överföra en Data Sources-fil

När du har förberett en datakälldatafil skickar du den till datakällor för bearbetning. Adobe har flera FTP-servrar för datakällor där du kan överföra datakällfiler. Tänk på följande om FTP-servrarna för datakällor:

* Välj FTP-information bredvid posten Datakälla på fliken [!UICONTROL Data Sources Manage] om du vill visa FTP-värd-, inloggnings- och lösenordsinformation för datakällans FTP-konto. Alla som har tillgång till den här informationen kan överföra data till rapportsviten.
* Av säkerhetsskäl stängs FTP-konton efter 30 dagars inaktivitet.
* FTP-konton är datakällsspecifika. Du kan inte använda ett FTP-konto för att överföra datakällfiler till flera datakällor.

**Så här överför du en datakällfil**

1. Använd en FTP-klient för att skicka data till din FTP-plats för datakällor.

   (Tillgängligt i länken FTP-information i Datakällshanteraren).

1. Överför en [!DNL .fin]-fil för att meddela Adobe om att överföringen av datakällfilen är slutförd.

   Filen [!DNL .fin] måste ha exakt samma namn som datakällfilen, förutom filtillägget. Adobe placerar inte datakällfilen i kö för bearbetning förrän du överför [!DNL .fin]-filen.

   Överför inte filen förrän alla datakällfiler har överförts. Annars kan datakällor försöka bearbeta en ofullständig fil.
1. När .fin-filen har överförts är det viktigt att du loggar ut från FTP-platsen för datakällor. Orsaken är att Analytics använder utloggningshändelser som utlösare för att ange att filerna är klara för bearbetning.
1. Håll utkik efter meddelanden under bearbetningen av datakällor.

   Hanteraren för datakällor visar eventuella fel som inträffar under filbearbetningen.
