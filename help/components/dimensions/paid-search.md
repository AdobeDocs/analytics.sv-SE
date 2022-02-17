---
title: Betalsökning
description: Skiljer statistik från betald och naturlig sökning.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Betalsökning

Med dimensionen Betalsökning kan du titta på alla mätvärden och jämföra dem mellan betalsökningar och naturlig sökning. Alla andra träffar utanför sökmotorer utelämnas. Denna dimension är användbar för att förstå hur dina betalda sökningar jämfört med organiska sökningar.

## Fyll den här dimensionen med data

Det enda kravet för att denna dimension ska fungera på rätt sätt är att ha [Påvisande av betald sökning](/help/admin/admin/paid-search-detection/paid-search-detection.md) korrekt konfigurerad i rapportsvitens inställningar. Om betalsökningsidentifiering är korrekt konfigurerat och en rapportserie har data fungerar alltid den här dimensionen.

## Dimensioner

Dimensioner innehåller två statiska värden: `"Natural"` och `"Paid"`. Om ett besök matchar villkoren för en sökmotor och även matchar betalsökningsidentifiering, tillhör det `"Paid"` dimensionsobjekt. Om ett besök uppfyller villkoren för en sökmotor och gör det *not* matchar betald sökningsidentifiering, den tillhör `"Natural"` dimensionsobjekt.
