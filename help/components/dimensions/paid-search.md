---
title: Betalsökning
description: Skiljer måtten från betald och naturlig sökning.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Betalsökning

Med &quot;betald sökning&quot; [dimension](overview.md) kan du titta på alla mått och jämföra dem mellan betald sökning och naturlig sökning. Alla andra träffar utanför sökmotorer utelämnas. Denna dimension är användbar för att förstå hur dina betalda sökningar jämfört med organiska sökningar.

## Fyll den här dimensionen med data

Det enda kravet för att den här dimensionen ska fungera korrekt är att [betald sökidentifiering](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) har konfigurerats korrekt i inställningarna för rapportsviten. Om betalsökningsidentifiering är korrekt konfigurerat och en rapportserie har data fungerar alltid den här dimensionen.

## Dimension-objekt

Dimension-objekt innehåller två statiska värden: `"Natural"` och `"Paid"`. Om ett besök uppfyller villkoren för en sökmotor och även matchar betalsökningsidentifiering, tillhör det dimensionsobjektet `"Paid"`. Om ett besök matchar villkoren för en sökmotor och *inte* matchar betalsökningsidentifiering, tillhör det dimensionsobjektet `"Natural"`.
