---
description: Kontrollera att ditt bibliotek för dynamisk tagghantering läses in korrekt på din plats.
keywords: Analysimplementering;implementeringsmetod;dynamisk tagghantering;dtm;kod;sidkod;sidhuvudskod;sidfotskod;inbäddningskod;verifiera kod;verifiera sidhuvudskod;verifiera sidfotskod;inbäddningsflik;inbädda
title: Verifiera sidhuvuds- och sidfotskod
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%

---

# Verifiera sidhuvuds- och sidfotskod

Kontrollera att ditt bibliotek för dynamisk tagghantering läses in korrekt på din plats.

1. Öppna webbplatsen i webbläsaren.
1. Öppna [!UICONTROL Developer Console] genom att högerklicka och välja **[!UICONTROL Inspect Element]** > **[!UICONTROL Console]**.
1. Tryck på **[!UICONTROL Enter]**.

   Om koden installerades korrekt visas *`true`* i konsolen.

   Om koden inte installerades korrekt visas referensfelet:

   `_satellite is not defined`

   Om du får det här felet bör du kontrollera att:

* Du har inkluderat den fullständiga huvudkoden på alla sidor på webbplatsen i [!DNL HEAD]-avsnittet, så nära `<head>`-taggen som möjligt.
* Det finns inga oväntade tecken i kodfragmentet, eventuellt till följd av kopiering och inklistring från ett formaterat dokument.
