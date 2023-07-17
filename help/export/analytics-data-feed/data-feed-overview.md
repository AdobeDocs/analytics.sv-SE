---
description: Data som samlas in från webbplatser, mobilappar eller överförs med hjälp av webbtjänste-API:er eller datakällor behandlas och lagras i Adobe Data warehouse. Dessa råa klickströmsdata utgör den datauppsättning som används av Adobe Analytics.
keywords: klickström;datafeed;datafeed;datafeed
title: Översikt över Analytics Data Feed
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 5%

---

# Översikt över Analytics Data Feed

Dataflöden är ett kraftfullt sätt att få ut rådata från Adobe Analytics. Dessa rådata kan användas på andra plattformar utanför Adobe efter eget gottfinnande. Data levereras i timbatchar vid varje timmes slut, eller i dagliga satser vid varje dags slut.

## Förutsättningar

Kontrollera att du uppfyller alla följande krav innan du använder dataflöden.

* En fungerande implementering som skickar data till Adobe datainsamlingsservrar. Se [Validera och publicera en implementering](/help/implement/launch/validate-publish-prod.md) i implementeringsguiden.
* Ditt konto är en produktadministratör för Analytics, eller så tillhör ditt konto en produktprofil med tillgång till dataflöden.
* En bucket konfigurerad på Amazon S3, Google Cloud Platform, Azure RBAC eller Azure SAS.
* (Äldre: Krävs endast för äldre måltyper för FTP och SFTP) Har en FTP-plats och autentiseringsuppgifter tillgängliga (FTP-autentiseringsuppgifter tillhandahålls av din organisation).

## Rekommenderade dataflödesresurser

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Navigera till Admin > Dataflöden i det övre navigeringsfältet.
4. Klicka på [!UICONTROL Add]. En ny sida med tre huvudkategorier visas: [!UICONTROL Feed information], [!UICONTROL Destination]och [!UICONTROL Data Column Definitions].
5. Fyll ut [!UICONTROL Feed Information] fält.
   * Namn: Alla önskade namn, till exempel &quot;Test data feed&quot;.
   * Rapportsvit: Välj önskad rapportsvit.
   * Mejla när det är klart: Ange din e-postadress.
   * Feedintervall: Välj önskat intervall (timme eller dag).
   * Fördröjning: Kan lämnas som [!UICONTROL No Delay].
   * Start- och slutdatum: Välj ett startdatum från flera dagar sedan och idag som slutdatum.
6. Fyll ut [!UICONTROL Destination] fält.
   * Typ: FTP
   * Värd: Ange önskad mål-URL för FTP. Exempel, `ftp://ftp.omniture.com`.
   * Sökväg: Kan lämnas tomt
   * Användarnamn: Ange användarnamnet för att logga in på FTP-platsen.
   * Lösenord och bekräfta lösenord: Ange lösenordet för att logga in på FTP-platsen.
7. Fyll ut [!UICONTROL Data Column Definitions].
   * Välj den senaste mallen All Adobe Columns (Alla) i listrutan.
   * Komprimeringsformat: Gzip
   * Paketeringstyp: Flera filer
   * Manifest: Ingen fil
8. Klicka [!UICONTROL Save] i det övre högra hörnet.
9. När data har sparats börjar den historiska databearbetningen. När data har bearbetats för en dag placeras filen på FTP-platsen.
10. Logga in på FTP-webbplatsen med Utforskaren i Windows eller en dedikerad FTP-klient.
11. Hämta den komprimerade datafeeden till din lokala dator.
12. Zippa upp den komprimerade filen med ett program som stöder `.tar.gz` filtillägg.
13. Öppna `hit_data.tsv` i kalkylbladet eller det databasprogram som du vill använda för att visa rådata för den dagen.

## Nästa steg

När ni förstår det grundläggande arbetsflödet för att hämta dataflöden kan ni arbeta med team inom organisationen för att lagra eller importera rådata till en databas.

* [Bästa praxis för dataflöden](/help/export/analytics-data-feed/data-feeds-best-practices.md): Bästa tillvägagångssätt för att skapa och hantera dataflöden.
* [Skapa en datafeed](create-feed.md): Teknisk information för att skapa en datafeed, förklara enskilda fält mer i detalj
* [Hantera dataflöden](df-manage-feeds.md): Läs mer om navigering i dataflödesgränssnittet
* [Innehåll i datafeed](c-df-contents/datafeeds-contents.md): Förstå vad som finns i den komprimerade filen <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Datakolumdefinitioner](c-df-contents/datafeeds-reference.md): En omfattande lista med alla tillgängliga kolumner.
* Video som navigerar i datafeedgränssnittet:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video om hur du hittar ditt datafeed-ID:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)