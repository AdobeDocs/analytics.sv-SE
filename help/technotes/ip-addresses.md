---
title: IP-adresser som används av Adobe Analytics
description: Om brandväggen blockerar IP-adresser som kommer från Adobe kan du uppdatera brandväggsinställningarna i den här listan.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# IP-adresser som används av Adobe Analytics

Vissa brandväggskonfigurationer blockerar IP-adresser som kommer från Adobe datainsamlingsservrar eller servrar som är ansvariga för dataåtkomst. Du kan använda den här listan med intervall för att ändra organisationens brandväggsinställningar så att åtkomst tillåts och data skickas inifrån organisationen.

Alla IP-adresser som används av Adobe Analytics ingår i [IP-adresser som används av Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses), med undantag för tilläggspaketet för Kina-prestandaoptimering.

## IP-adresser för prestandaoptimering i Kina

Tilläggspaketet för prestandaoptimering i Kina är en extra betaltjänst som förbättrar AppMeasurementets datainsamling för besökare i Kina. Kontakta kontoteamet på Adobe om du vill veta mer om hur du använder den här funktionen.

>[!IMPORTANT]
>
>China RDC är inte tillgängligt för Web SDK-datainsamling. De här AppMeasurementen gäller endast för serverbibliotek.

Regionala datainsamlingsservrar i Kina använder följande IP-adresser:

| Plats | Värd |
| --- | --- |
| Kina | `52.80.168.159` |
| Kina | `52.80.199.104` |
| Kina | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[IP-adresser som används av Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domäner som används av Adobe Analytics](domains.md)
