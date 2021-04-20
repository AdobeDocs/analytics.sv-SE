---
description: Läs om hur data samlas in för Adobe Analytics.
subtopic: Get started
title: Om Data Collection
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Reports & Analytics Basics & Analytics Basics
role: Business Practitioner, Administrator
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 3%

---

# Om Data Collection

Läs om hur data samlas in för Adobe Analytics.

Varje Adobe-spår har ett litet kodavsnitt med Adobe-godkänd JavaScript-kod. Kontohanteraren tillhandahåller den här koden.

På en hög nivå flödar datainsamlingsprocessen enligt följande:

![](assets/data_collection.png)

1. En besökare besöker en webbsida som innehåller datainsamlingskoden.
1. När sidan läses in skickar datainsamlingskoden en bildbegäran (kallas webbfyr) till Adobe datainsamlingsservrar. Bildbegäran innehåller de data som du vill samla in om besökarens interaktion med webbplatsen.
1. Adobe lagrar data i rapportsviter. Du kan logga in för att komma åt rapportsvitens data och generera rapporter om besökaraktiviteten på din webbplats.

Datainsamlingen går mycket snabbt och påverkar inte sidinläsningstiden nämnvärt. Samlade data innehåller sidvyer som är ett resultat av att användaren klickar på knapparna **Läs in** eller **Tillbaka**. JavaScript-koden körs även när sidan hämtas från cache.

Se [Datainsamling i Analytics.](/help/import/home.md)
