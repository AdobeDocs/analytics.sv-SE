---
title: Användargränssnitt för datafeed
description: Lär dig navigera i dataflödesgränssnittet.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 1%

---

# Hantera dataflöden

Med dataflödeshanteraren kan du skapa, redigera och ta bort dataflöden för din organisation. Om du har behörighet att komma åt dataflödeshanteraren kan du hantera dataflöden för alla rapportsviter som är synliga för dig.

Här är en video om gränssnittet för hantering av dataflöden:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Få åtkomst till dataflödeshantering genom att följa dessa steg:

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analyser**].
1. I det övre navigeringsfältet går du till [!UICONTROL **Administratör**] > [!UICONTROL **Dataflöden**].

## Navigera i gränssnittet

Gränssnittet ser ut ungefär så här när du kommer till sidan för dataflödeshanteraren:

![Dataflöden](assets/feeds.png)

Om inga feeds har konfigurerats visas en [!UICONTROL Create New Data Feed] -knappen.

### Filter och sökning

Använd sökning eller filter för att hitta en viss feed.

* Börja skriva namnet på en feed i sökfältet. Endast de feeds som matchar visas i listan över tillgängliga feeds.

* Klicka på filterikonen längst till vänster om du vill visa eller dölja filteralternativen. Filter ordnas efter kategori. Du kan komprimera eller utöka filtreringskategorier. Markera kryssrutan bredvid de filter du vill använda.

  ![Filter](assets/filters.png)

### Feeds och jobb

Välj [!UICONTROL **Jobb**] för att visa enskilda jobb som var och en av dina feeds skapar. Se [Hantera datafeedjobb](df-manage-jobs.md).

### Lägg till

The [!UICONTROL Add] kan du skapa en ny feed. Se [Skapa en datafeed](create-feed.md) för mer information.

### Kolumner

Varje feed som skapas visar flera kolumner med information om den. Välj en kolumnrubrik om du vill sortera den i stigande ordning. Välj en kolumnrubrik igen om du vill sortera den i fallande ordning. Om du inte kan se en viss kolumn klickar du på kolumnikonen i det övre högra hörnet.

![Kolumnikon](assets/cols.jpg)

* **Feednamn**: Obligatorisk kolumn. Visar feed-namnet.
* **Feed-ID**: Visar feed-ID:t, en unik identifierare.
* **Report Suite**: Rapportsviten innehåller de data som matningen refererar till.
* **Report Suite-ID**: Rapportsvitens unika identifierare.
* **Datakolumner**: Vilka datakolumner som är aktiva för feeden. I de flesta fall finns det för många kolumner att visa i det här formatet.
* **Intervall**: Anger om matningen är timme eller dag.
* **Måltyp**: Måltypen för feeden. Exempel: Amazon S3, GCP eller Azure.
* **Målvärd**: Platsen där filen placeras.
* **Ägare**: Användarkontot som skapade feeden.
* **Status**: Status för feeden.
   * Aktiv: Matningen är i drift.
   * Väntande godkännande: I vissa fall måste en feed godkännas av Adobe innan den kan börja generera jobb.
   * Borttagen: Matningen tas bort.
   * Slutförd: Flödet har bearbetats färdigt. En ifylld feed kan redigeras, stoppas eller avbrytas.
   * Väntande: Matningen har skapats men är ännu inte aktiv. Feeds finns kvar i detta tillstånd under en kort övergångsperiod.
   * Inaktiv: Motsvarar ett pausat eller spärrat läge. Om en återfyllningsfeed (en feed som endast bearbetar historiska data) återaktiveras, kommer den att fortsätta leverera jobb från när den stoppas. Om en livefeed återaktiveras fortsätter den att leverera jobb från och med när den stoppas.
* **Senast ändrad**: Det datum då feeden senast ändrades. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning.
* **Startdatum**: Datumet för det första jobbet för denna feed. Datum och tid visas i rapportsvitens tidszon med GMT-förskjutning.
* **Slutdatum**: Datum för det senaste jobbet för denna feed. Pågående dataflöden har inget slutdatum.

## Åtgärder för datafeed

Klicka i kryssrutan bredvid en datafeed för att visa tillgängliga åtgärder.

* **Jobbhistorik**: Visa alla jobb som är kopplade till dessa dataflöden. Tar dig automatiskt till [gränssnitt för hantering av jobb](df-manage-jobs.md).
* **Ta bort**: Tar bort dataflödet och anger dess status till [!UICONTROL Deleted].
* **Kopiera**: Tar dig till [skapa en ny feed](create-feed.md) med alla inställningar för aktuell feed. Du kan inte kopiera en datafeed om mer än en har valts.
* **Pausa**: Stoppar bearbetningen av feeden och anger dess status som [!UICONTROL Inactive].
* **Aktivera**: Endast tillgängligt för inaktiva feeds. Förifyllda feeds (feeds som endast bearbetar historiska data) återupptar bearbetningen av data från där de stoppades och fyller eventuellt inte i alla datum om det behövs. Live-flöden återupptar bearbetning av data från den aktuella tiden.
