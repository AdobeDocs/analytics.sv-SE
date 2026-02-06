---
title: Hantera dataflödesjobb
description: Lär dig hur du hanterar enskilda jobb i dataflöden. Navigera i gränssnittet, använd filter och sök, och hitta kolumndefinitioner.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: 728e807764901ad2bd6834339e5e75348dd5a988
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 1%

---

# Hantera datafeedjobb

Jobb är enskilda uppgifter som returnerar en komprimerad fil. De skapas och styrs av feeds.

Så här hanterar du dataflödesjobb:

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.

1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analytics**].

1. Gå till [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**] i det övre navigeringsfältet.

   Dataflöden för alla rapportsviter som du har åtkomst till visas. Om inga feeds har konfigurerats visas knappen [!UICONTROL Create New Data Feed] på sidan.

   ![Dataflödeshanteraren](assets/data-feed-manager.png)

1. (Valfritt) Markera kryssrutan bredvid dataflödet som innehåller de jobb som du vill visa och välj sedan [!UICONTROL **Jobbhistorik**].

   Mer information finns i [Visa jobbhistorik för en datafeed](#view-job-history-for-a-data-feed).

## Filtrera och söka

Du kan filtrera och söka efter exakt det jobb du letar efter.

Klicka på filterikonen längst till vänster om du vill visa eller dölja filteralternativen. Filter ordnas efter kategori. Klicka på avrivningen om du vill komprimera eller utöka filterkategorierna. Klicka i kryssrutan för att använda ett filter.

![Filter](assets/jobs-filter.png)

Använd sökning för att hitta ett jobb efter namn.

![Sök](assets/search.png)

## Sortera och anpassa kolumner

Varje jobb visar flera kolumner med information om jobbet. Du kan sortera information i varje kolumn och anpassa de kolumner som visas.

### Sortera kolumner

Välj en kolumnrubrik om du vill sortera den i stigande ordning. Välj en kolumnrubrik igen om du vill sortera den i fallande ordning.

### Anpassa kolumner

Så här justerar du synliga kolumner i tabellen:

1. Markera kolumnikonen ![Kolumnikon](assets/customize-columns-icon.png) i det övre högra hörnet.

1. I dialogrutan Anpassa tabell markerar du de kolumner som du vill visa och avmarkerar de kolumner som du vill dölja.

   Följande kolumner är tillgängliga:

* **Feed-namn**: Obligatorisk kolumn. Visar feed-namnet. Jobb som skapas av samma feed har samma feed-namn.
* **Feed-ID**: Visar feed-ID:t, en unik identifierare. Jobb som skapas av samma feed har samma feed-ID.
* **Rapportsviten**: Rapportsviten som jobbet refererar till data från.
* **Rapportsvitens ID**: Rapportsvitens unika identifierare.
* **Intervall**: Intervallet för feeden.
* **Måltyp**: Måltypen för feeden.
* **Mål**: Flödets mål.
* **Ägare**: Ägaren till feeden.
* **Status**: Status för feeden.
   * Väntar på data: Jobbet är i drift och data för rapportfönstret samlas in.
   * Bearbetning: Jobbet skapar datafilerna och förbereder att skicka dem.
   * Slutförd: Jobbet slutfördes utan problem.
   * Misslyckades: Jobbet slutfördes inte. Se [Felsöka datafeeds](troubleshooting.md) för att fastställa orsaken till felet.
   * Väntar på export: Data för rapportfönstret har ännu inte bearbetats fullständigt.
   * Inga data: Det finns inga data i rapportsviten för det begärda rapportfönstret.
* **Senast ändrad**: Den tidpunkt då feeden senast ändrades.
* **Startdatum**: Den tidpunkt då jobbet startades. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning. Dagliga matningar börjar vanligtvis nära midnatt i rapportsvitens tidszon.
* **Slutdatum**: Den tidpunkt då jobbet avslutades. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning.

## Visa jobbhistorik för en datafeed

Du kan visa en lista över tidigare datafeedjobb för en given datafeed, tillsammans med information om varje jobb.

Så här visar du jobbhistorik för en datafeed:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

   ![Dataflödeshanteraren](assets/data-feed-manager.png)

1. Markera kryssrutan bredvid den datafeed vars jobbhistorik du vill visa och välj sedan [!UICONTROL **Jobbhistorik**].

   Jobbhistorik för datafeed visas, med följande information tillgänglig om varje jobb (markera kolumnikonen för att lägga till kolumner som inte är synliga som standard):

   * **[!UICONTROL Request period begin]**

   * **[!UICONTROL Request period end]**

   * **[!UICONTROL Scheduled]**

   * **[!UICONTROL Started]**

   * **[!UICONTROL Finished]**

   * **[!UICONTROL Run #]**

   * **[!UICONTROL Status]**

   * **[!UICONTROL Error code]**

   * **[!UICONTROL Error message]**

## Återställa datafeedjobb

Du kan skicka om ett datafeedjobb om du vill skicka datafeedfilen igen med exakt samma data och bearbetning som när den ursprungligen skickades. Du kan också [bearbeta om ett datafeedjobb](#reprocess-data-feed-jobs).

Så här skickar du om ett eller flera datafeedjobb:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som innehåller de jobb som du vill skicka om och välj sedan [!UICONTROL **Jobbhistorik**].

1. Markera kryssrutan bredvid ett eller flera datafeedjobb och välj sedan **[!UICONTROL Resend]**. <!-- What does the status need to be? Error, ... -->

   ![Bearbeta om datafeedjobb](assets/data-feed-job-resend.png)

## Bearbeta datafeedjobb igen

Du kan bearbeta om källdata för ett datafeedjobb och skicka det igen med de ombearbetade data. Du kan också [skicka om ett datafeedjobb](#resend-data-feed-jobs).

Så här bearbetar du om ett eller flera datafeedjobb:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som innehåller de jobb som du vill bearbeta igen och välj sedan [!UICONTROL **Jobbhistorik**].

1. Markera kryssrutan bredvid ett eller flera datafeedjobb och välj sedan **[!UICONTROL Reprocess]**. <!-- What does the status need to be? Error, ... -->

   ![Bearbeta om datafeedjobb](assets/data-feed-job-reprocess.png)
