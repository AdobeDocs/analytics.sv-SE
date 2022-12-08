---
title: Betalsökning
description: Skiljer statistik från betald och naturlig sökning.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Betalsökning

Med dimensionen Betalsökning kan du titta på alla mätvärden och jämföra dem mellan betalsökningar och naturlig sökning. Alla andra träffar utanför sökmotorer utelämnas. Denna dimension är användbar för att förstå hur dina betalda sökningar jämfört med organiska sökningar.

## Fyll den här dimensionen med data

Det enda kravet för att denna dimension ska fungera på rätt sätt är att ha [Påvisande av betald sökning](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) korrekt konfigurerad i rapportsvitens inställningar. Om betalsökningsidentifiering är korrekt konfigurerat och en rapportserie har data fungerar alltid den här dimensionen.

## Dimensioner

Dimensioner innehåller två statiska värden: `"Natural"` och `"Paid"`. Om ett besök matchar villkoren för en sökmotor och även matchar betalsökningsidentifiering, tillhör det `"Paid"` dimensionsobjekt. Om ett besök uppfyller villkoren för en sökmotor och gör det *not* matchar betald sökningsidentifiering, den tillhör `"Natural"` dimensionsobjekt.
