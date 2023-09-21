---
title: Betalsökning
description: Skiljer måtten från betald och naturlig sökning.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Betalsökning

&quot;Betalsökning&quot; [dimension](overview.md) Med kan du titta på alla mätvärden och jämföra dem mellan betalsökningar och naturtrogna sökningar. Alla andra träffar utanför sökmotorer utelämnas. Denna dimension är användbar för att förstå hur dina betalda sökningar jämfört med organiska sökningar.

## Fyll den här dimensionen med data

Det enda kravet för att denna dimension ska fungera på rätt sätt är att ha [Påvisande av betald sökning](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) korrekt konfigurerad i rapportsvitens inställningar. Om betalsökningsidentifiering är korrekt konfigurerat och en rapportserie har data fungerar alltid den här dimensionen.

## Dimensioner

Dimensioner innehåller två statiska värden: `"Natural"` och `"Paid"`. Om ett besök matchar villkoren för en sökmotor och även matchar betalsökningsidentifiering, tillhör det `"Paid"` dimensionsobjekt. Om ett besök uppfyller villkoren för en sökmotor och gör det *not* matchar betald sökidentifiering, den tillhör `"Natural"` dimensionsobjekt.
