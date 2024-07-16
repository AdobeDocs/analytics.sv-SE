---
title: Användargränssnitt för datafeed
description: Lär dig navigera i dataflödesgränssnittet.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: e7e03531454bd56ebe6152edc08765f42ebec728
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 0%

---

# Hantera dataflöden

Med dataflödeshanteraren kan du skapa, redigera och ta bort dataflöden för din organisation. Om du har behörighet att komma åt dataflödeshanteraren kan du hantera dataflöden för alla rapportsviter som är synliga för dig.

+++Visa en video om dataflödeshantering.

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

+++

## Visa dataflöden

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analytics**].
1. Gå till [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**] i det övre navigeringsfältet.

   Dataflöden för alla rapportsviter som du har åtkomst till visas. Om inga feeds har konfigurerats visas knappen [!UICONTROL Create New Data Feed] på sidan.

   ![Dataflöden](assets/feeds.png)

## Skapa en datafeed

Med knappen [!UICONTROL Add] kan du skapa en ny feed. Mer information finns i [Skapa en datafeed](create-feed.md).

## Redigera en datafeed

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Leta reda på den datafeed som du vill redigera. Om du vill söka efter en datafeed kan du [filtrera och söka i listan med datafeeds](#filter-and-search-the-list-of-data-feeds).

1. Markera datafeeden i kolumnen [!UICONTROL **Feed name**].

1. Gör eventuella ändringar i dataflödet.

   När du uppdaterar avsnittet [!UICONTROL **Mål**] för en datafeed som du redigerar kan du välja ett annat konto och en annan plats att använda för den nya datafeeden i listrutorna [!UICONTROL **Konto**] och [!UICONTROL **Plats**] .

   Konton och platser kan redigeras på det sätt som beskrivs i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md). Om du redigerar ett konto eller en plats påverkas alla objekt som är kopplade till kontot eller platsen.

   I tidigare versioner av dataflödeshanteraren kunde du skapa FTP-, SFTP-, S3- och Azure-blobmål. Destinationer som skapades i dessa tidigare versioner av dataflödeshanteraren kan inte redigeras eller kopieras.

1. Välj [!UICONTROL **Spara**].

## Filtrera och söka i listan med dataflöden

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Använd sökning eller filter för att hitta en viss feed.

   * Börja skriva namnet på en feed i sökfältet. Endast de feeds som matchar visas i listan över tillgängliga feeds.

   * Klicka på filterikonen längst till vänster om du vill visa eller dölja filteralternativen. Filter ordnas efter kategori. Du kan komprimera eller utöka filtreringskategorier. Markera kryssrutan bredvid de filter du vill använda.

![Filter](assets/filters.png)

## Visa dataflödesjobb

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Välj fliken [!UICONTROL **Jobb**] om du vill visa enskilda jobb som var och en av dina feeds skapar.

   eller

   Om du vill visa jobb för specifika dataflöden markerar du kryssrutan bredvid en eller flera dataflöden och väljer sedan [!UICONTROL **Jobbhistorik**].

   Mer information finns i [Hantera datafeedjobb](df-manage-jobs.md).

## Kopiera en datafeed

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som du vill kopiera och välj sedan [!UICONTROL **Kopiera**].

   Tar dig till [skapa en ny feed](create-feed.md) med alla inställningar för den aktuella feeden. Det här alternativet är inte synligt om mer än en datafeed har valts.

   När du uppdaterar avsnittet [!UICONTROL **Mål**] för en datafeed som du kopierar kan du välja ett annat konto och en annan plats att använda för den nya datafeeden i listrutorna [!UICONTROL **Konto**] och [!UICONTROL **Plats**] .

   Konton och platser kan redigeras på det sätt som beskrivs i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md) och [Konfigurera molnimport- och exportplatser](/help/components/locations/configure-import-locations.md). Om du redigerar ett konto eller en plats påverkas alla objekt som är kopplade till kontot eller platsen.

   I tidigare versioner av dataflödeshanteraren kunde du skapa FTP-, SFTP-, S3- och Azure-blobmål. Destinationer som skapades i dessa tidigare versioner av dataflödeshanteraren kan inte redigeras eller kopieras.

## Pausa en datafeed

Du kan stoppa bearbetningen för feeden och ange dess status till [!UICONTROL Inactive].

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som du vill pausa och välj sedan [!UICONTROL **Paus**].

## Aktivera en datafeed

Du kan aktivera inaktiva feeds.

Förifyllda feeds (feeds som endast bearbetar historiska data) återupptar bearbetningen av data från där de stoppades och fyller eventuellt inte i alla datum om det behövs. Live-flöden återupptar också databearbetning från där de stoppades.

>[!AVAILABILITY]
>
>Följande ändring av hur live-flöden återupptar databearbetning finns i den begränsade testfasen av releasen:
> 
>**Live-flöden återupptar databearbetning från den aktuella tiden.**
>
>Den här ändringen kanske inte är tillgänglig än i din miljö.
>
>Den här anteckningen tas bort när den här ändringen är allmänt tillgänglig. Mer information om Analytics-releaser finns i [Adobe Analytics-funktionsreleaser](/help/release-notes/releases.md).

Så här aktiverar du en datafeed:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den inaktiva datafeed som du vill aktivera och välj sedan [!UICONTROL **Aktivera**].

## Ta bort en datafeed

När du tar bort en datafeed anges dess status till [!UICONTROL Deleted]. Dataflöden måste ha statusen Aktiv innan de kan tas bort.

Så här tar du bort en datafeed:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som du vill ta bort och välj sedan [!UICONTROL **Ta bort**].

## Konfigurera kolumner i dataflödeshanteraren

Varje feed som skapas visar flera kolumner med information om den. Välj en kolumnrubrik om du vill sortera den i stigande ordning. Välj en kolumnrubrik igen om du vill sortera den i fallande ordning. Om du inte kan se en viss kolumn klickar du på kolumnikonen i det övre högra hörnet.

![Kolumnikon](assets/cols.jpg)

Följande kolumner är tillgängliga:

* **Feed-namn**: Obligatorisk kolumn. Visar feed-namnet.
* **Feed-ID**: Visar feed-ID:t, en unik identifierare.
* **Rapportsviten**: Rapportsviten som matningsreferensdata kommer från.
* **Rapportsvitens ID**: Rapportsvitens unika identifierare.
* **Datakolumner**: Vilka datakolumner som är aktiva för feeden. I de flesta fall finns det för många kolumner att visa i det här formatet.
* **Intervall**: Indikerar om matningen är timme eller dag.
* **Måltyp**: Måltypen för feeden. Exempel: Amazon S3, GCP eller Azure.
* **Målvärd**: Platsen där filen placeras.
* **Ägare**: Användarkontot som skapade feeden.
* **Status**: Status för feeden.
   * Aktiv: Matningen är i drift.
   * Väntande godkännande: I vissa fall måste en feed godkännas av Adobe innan den kan börja generera jobb.
   * Borttagen: Matningen tas bort.
   * Slutförd: Flödet har bearbetats färdigt. En ifylld feed kan redigeras, stoppas eller avbrytas.
   * Väntande: Matningen har skapats men är ännu inte aktiv. Feeds finns kvar i detta tillstånd under en kort övergångsperiod.
   * Inaktiv: Motsvarar ett pausat eller spärrat läge. Mer information om vad som händer med födofyllnadsflöden och livefeeds när en inaktiv feed återaktiveras finns i [Aktivera en datafeed](#activate-a-data-feed).
* **Senast ändrad**: Det datum då feeden senast ändrades. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning.
* **Startdatum**: Datumet för det första jobbet för denna feed. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning.
* **Slutdatum**: Datumet för det senaste jobbet för denna feed. Pågående dataflöden har inget slutdatum.

