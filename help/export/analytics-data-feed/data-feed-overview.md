---
description: Data som samlas in från webbplatser, mobilappar eller överförs med hjälp av webbtjänste-API:er eller datakällor behandlas och lagras i Adobe Data warehouse. Dessa råa klickströmsdata utgör den datauppsättning som används av Adobe Analytics.
keywords: klickström;datafeed;datafeed;datafeed
title: Översikt över Analytics Data Feed
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 84bdeb5d502e46c922fc5123fcdd5b6819426c0e
workflow-type: tm+mt
source-wordcount: '314'
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
* [Hantera dataflöden](df-manage-feeds.md): Läs mer om navigering i dataflödesgränssnittet
* [Innehåll i datafeed](c-df-contents/datafeeds-contents.md): Förstå vad som finns i den komprimerade filen <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Datakolumdefinitioner](c-df-contents/datafeeds-reference.md): En omfattande lista med alla tillgängliga kolumner.
* Video som navigerar i datafeedgränssnittet:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video om hur du hittar ditt datafeed-ID:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)