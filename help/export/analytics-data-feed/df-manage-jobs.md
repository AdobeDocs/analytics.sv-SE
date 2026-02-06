---
title: Hantera dataflödesjobb
description: Lär dig hur du hanterar enskilda jobb i dataflöden. Navigera i gränssnittet, använd filter och sök, och hitta kolumndefinitioner.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---

# Hantera datafeedjobb

Jobb är enskilda uppgifter som genererar en komprimerad fil. De skapas och styrs av feeds.

Du kan visa jobbhistoriken för varje datafeed, skicka om jobb eller bearbeta om jobb.

## Visa jobbhistorik för en datafeed

Du kan visa en lista med dataflödesjobb för en given datafeed, tillsammans med information om varje jobb.

Så här visar du jobbhistorik för en datafeed:

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.

1. Markera ikonen med nio kvadrater i det övre högra hörnet och välj sedan [!UICONTROL **Analytics**].

1. Gå till [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**] i det övre navigeringsfältet.

   Dataflöden för alla rapportsviter som du har åtkomst till visas. Om inga feeds har konfigurerats visas knappen **[!UICONTROL Create data feed]** på sidan.

   ![Dataflödeshanteraren](assets/data-feed-manager.png)

1. Markera kryssrutan bredvid den datafeed som innehåller de jobb som du vill visa och välj sedan [!UICONTROL **Jobbhistorik**].

   Jobbhistorik för datafeed visas, med information om varje jobb i de tillgängliga kolumnerna.

1. (Valfritt) Om du vill justera de synliga kolumnerna i tabellen markerar du kolumnikonen ![Kolumn-ikonen](assets/customize-columns-icon.png) i det övre högra hörnet. I dialogrutan Anpassa tabell markerar du de kolumner som du vill visa och avmarkerar de kolumner som du vill dölja.

   Följande kolumner är tillgängliga:

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

När du skickar om ett datafeed-jobb skickas datafeedfilen igen med samma data och bearbetning som när filen ursprungligen skickades. Du kan också [bearbeta om ett datafeedjobb](#reprocess-data-feed-jobs).

Så här skickar du om ett eller flera datafeedjobb:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som innehåller de jobb som du vill skicka om och välj sedan [!UICONTROL **Jobbhistorik**].

1. Markera kryssrutan bredvid ett eller flera datafeedjobb och välj sedan **[!UICONTROL Resend]**. <!-- What does the status need to be? Error, ... -->

   ![Bearbeta om datafeedjobb](assets/data-feed-job-resend.png)

## Bearbeta datafeedjobb igen

När du bearbetar om ett datafeedjobb bearbetas källdata om i ett datafeedjobb och skickas igen med de ombearbetade data. Du kan också [skicka om ett datafeedjobb](#resend-data-feed-jobs).

Så här bearbetar du om ett eller flera datafeedjobb:

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Dataflöden**].

1. Markera kryssrutan bredvid den datafeed som innehåller de jobb som du vill bearbeta igen och välj sedan [!UICONTROL **Jobbhistorik**].

1. Markera kryssrutan bredvid ett eller flera datafeedjobb och välj sedan **[!UICONTROL Reprocess]**. <!-- What does the status need to be? Error, ... -->

   ![Bearbeta om datafeedjobb](assets/data-feed-job-reprocess.png)
