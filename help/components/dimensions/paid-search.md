---
title: Betalsökning
description: Skiljer statistik från betald och naturlig sökning.
translation-type: tm+mt
source-git-commit: d71edc74644907b47bfb6492e7a6c47c06d5984f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Betalsökning

Med dimensionen Betalsökning kan du titta på alla mätvärden och jämföra dem mellan betalsökningar och naturlig sökning. Alla andra träffar utanför sökmotorer utelämnas. Denna dimension är användbar för att förstå hur dina betalda sökningar jämfört med organiska sökningar.

## Fyll den här dimensionen med data

Det enda kravet för att den här dimensionen ska fungera korrekt är att [betalsökningsidentifiering](/help/admin/admin/paid-search-detection/paid-search-detection.md) är korrekt konfigurerat i rapportsvitens inställningar. Om betalsökningsidentifiering är korrekt konfigurerat och en rapportserie har data fungerar alltid den här dimensionen.

## Dimensionsvärden

Dimensionsvärden innehåller två statiska värden: `"Natural"` och `"Paid"`. Om ett besök matchar villkoren för en sökmotor och även matchar betalsökningsidentifiering, hör det till `"Paid"` dimensionsvärdet. Om ett besök matchar villkoren för en sökmotor och *inte* matchar betald sökningsidentifiering, hör det till `"Natural"` dimensionsvärdet.
