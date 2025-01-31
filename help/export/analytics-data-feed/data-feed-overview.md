---
description: Lär dig hur du använder dataflöden för att få ut rådata från Adobe Analytics. Ta reda på vad som krävs för att använda dataflöden.
keywords: klickström;datafeed;datafeed;datafeed
title: Översikt över Analytics-dataflöden
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Översikt över Analytics Data Feed

Dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. Dessa rådata kan användas på andra plattformar utanför Adobe efter eget gottfinnande. Data levereras i timbatchar vid varje timmes slut, eller i dagliga satser vid varje dags slut.

## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder dataflöden.

* En fungerande implementering som skickar data till Adobe datainsamlingsservrar. Se [Validera och publicera en implementering](/help/implement/launch/validate-publish-prod.md) i implementeringsguiden.
* Ditt konto är en produktadministratör för Analytics, eller så tillhör ditt konto en produktprofil med tillgång till dataflöden.
* En bucket konfigurerad på Amazon S3, Google Cloud Platform, Azure RBAC eller Azure SAS.
* (Äldre: Krävs endast för äldre måltyper för FTP och SFTP) Har en FTP-plats och autentiseringsuppgifter tillgängliga (FTP-autentiseringsuppgifter tillhandahålls av din organisation).

## Nästa steg

Följande resurser hjälper dig att förstå det grundläggande arbetsflödet för att hämta dataflöden. När du har förstått det grundläggande arbetsflödet kan du arbeta med team inom organisationen för att lagra eller importera rådata till en databas.

* [Bästa praxis för dataflöden](/help/export/analytics-data-feed/data-feeds-best-practices.md): Bästa tillvägagångssätt för att skapa och hantera dataflöden.
* [Skapa en datafeed](create-feed.md): Teknisk information för att skapa en datafeed, förklara enskilda fält mer i detalj
* [Hantera dataflöden](df-manage-feeds.md): Läs mer om hur du navigerar i datafeedgränssnittet
* [Innehåll i datafeed](c-df-contents/datafeeds-contents.md): Förstå vad som finns i den komprimerade filen <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Datakolumndefinitioner](c-df-contents/datafeeds-reference.md): En omfattande lista över alla tillgängliga kolumner.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navigera i dataflödesgränssnittet](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hitta ditt datafeed-id](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]
