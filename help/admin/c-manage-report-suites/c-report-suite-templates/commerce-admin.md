---
description: Definierar vanliga inställningar för en e-handelswebbplats.
title: Handel
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# Handel

Definierar vanliga inställningar för en e-handelswebbplats.

| Konverteringsvariabler | Typ | Underordnade relationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Interna kampanjer | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar2` |
| Marknadsföringskategori | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar3` |
| Handelsvariabel 4 | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar4` |
| Handelsvariabel 5 | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar5` |

| Success Events | Typ | `s_code` variabel |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| Anpassade händelser 1-5 | Räknare (inga underrelationer) | `event1, event2, event3, event4, event5` |

| Custom Insight Variables | `s_code` variabel |
|---|---|
| Trafikegenskap 1-5 | `prop1, prop2, prop3, prop4, prop5` |

Följande tabell innehåller en lista med standardhändelser för e-handel. Den första konfigurationen för dessa händelser är identisk i alla rapportsvitmallar. Händelser med s_code-variabeln N/A behöver inte anges, de tillhandahålls automatiskt.

| Standardhandelshändelser | Typ | `s_code` variabel |
|---|---|---|
| Intäkter | Räknare | `purchase` |
| Beställningar | Räknare | `purchase` |
| Enheter | Räknare | `purchase` |
| Korgar | Räknare | `scOpen` |
| Kundvagnsvisningar | Räknare | `scView` |
| Instanser | Räknare | Ej tillämpligt |
| Utcheckningar | Räknare | `scCheckout` |
| Tillägg i kundvagn | Räknare | `scAdd` |
| Raderingar i kundvagn | Räknare | `scRemove` |
| Besök | Räknare (inga underrelationer) | Ej tillämpligt |
| Sidvisningar | Räknare (inga underrelationer) | Ej tillämpligt |
| Dagliga unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
| Unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
