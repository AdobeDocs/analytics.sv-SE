---
description: Du kan matcha värden mot vanliga felstavningar och uppdatera dem så att de visas korrekt i rapporter.
subtopic: Processing rules
title: Rensa värden i en rapport
topic: Admin tools
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

