---
description: Kontrollera att ditt bibliotek för dynamisk tagghantering läses in korrekt på din plats.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Verifiera sidhuvuds- och sidfotskod
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 7%

---


# Verifiera sidhuvuds- och sidfotskod

Kontrollera att ditt bibliotek för dynamisk tagghantering läses in korrekt på din plats.

1. Öppna webbplatsen i webbläsaren.
1. Öppna [!UICONTROL Developer Console] genom att högerklicka och välja **[!UICONTROL Inspect Element]** > **[!UICONTROL Console]**.
1. Tryck **[!UICONTROL Enter]**.

   Om koden har installerats på rätt sätt visas *`true`* den i konsolen.

   Om koden inte installerades korrekt visas referensfelet:

   `_satellite is not defined`

   Om du får det här felet bör du kontrollera att:

* Du har inkluderat den fullständiga sidhuvudskoden på alla sidor på webbplatsen i [!DNL HEAD] -avsnittet så nära `<head>` -taggen som möjligt.
* Det finns inga oväntade tecken i kodfragmentet, eventuellt till följd av kopiering och inklistring från ett formaterat dokument.

