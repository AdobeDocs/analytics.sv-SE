---
description: Läs om hur data samlas in för Adobe Analytics.
subtopic: Get started
title: Om datainsamling
topic: Reports and analytics
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Om datainsamling

Läs om hur data samlas in för Adobe Analytics.

På varje sida har Adobe-spåren ett litet kodavsnitt med Adobe-godkänd JavaScript-kod. Kontohanteraren tillhandahåller den här koden.

På en hög nivå flödar datainsamlingsprocessen enligt följande:

![](assets/data_collection.png)

1. En besökare besöker en webbsida som innehåller datainsamlingskoden.
1. När sidan läses in skickar datainsamlingskoden en bildbegäran (kallas webbfyr) till Adobes datainsamlingsservrar. Bildbegäran innehåller de data som du vill samla in om besökarens interaktion med webbplatsen.
1. Adobe lagrar data i rapportsviter. Du kan logga in för att komma åt rapportsvitens data och generera rapporter om besökaraktiviteten på din webbplats.

Datainsamlingen går mycket snabbt och påverkar inte sidinläsningstiden nämnvärt. Samlade data innehåller sidvyer som är ett resultat av att du klickar på webbläsarens **knappar Läs in** igen eller **Bakåt** . JavaScript-koden körs även när sidan hämtas från cache.

Se [Datainsamling i Analytics.](/help/import/home.md)
