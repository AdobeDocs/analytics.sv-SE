---
description: Du kan matcha värden mot vanliga felstavningar och uppdatera dem så att de visas korrekt i rapporter.
subtopic: Processing rules
title: Rensa värden i en rapport
feature: Admin Tools
role: Admin
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Rensa värden i en rapport

Du kan matcha värden mot vanliga felstavningar och uppdatera dem så att de visas korrekt i rapporter.

Om du vill vara säker på att du inte oavsiktligt matchar andra värden använder du det mest restriktiva matchningsalternativet som är tillgängligt. Du kan köra en rapport på variabeln (prop1 i exemplet nedan) och söka efter de termer som du väljer att ersätta för att se till att de inte matchar oönskade värden. Strängjämförelser är inte skiftlägeskänsliga.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om prop1 börjar med att handla |
| Åtgärd | Skriv över värdet för prop1 till köp av anpassat värde |

Exempel:

![](assets/clean-up-values-in-report.png)
