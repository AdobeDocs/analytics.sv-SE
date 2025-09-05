---
description: Definierar vanliga inställningar för en e-handelswebbplats.
title: Commerce
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 11%

---

# Commerce

Definierar vanliga inställningar för en e-handelswebbplats.

| Konverteringsvariabler | Typ | Underrelationer | Allokering | Förfallotid | Variabeln `s_code` |
|---|---|---|---|---|---|
| Interna kampanjer | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Marknadsföringskategori | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |
| Commerce Variable 4 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar4` |
| Commerce Variable 5 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar5` |

| Success Events | Typ | Variabeln `s_code` |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| Anpassade händelser 1-5 | Räknare (inga underrelationer) | `event1, event2, event3, event4, event5` |

| Custom Insight Variables | Variabeln `s_code` |
|---|---|
| Trafikegenskap 1-5 | `prop1, prop2, prop3, prop4, prop5` |

Följande tabell innehåller en lista med standardhändelser för e-handel. Den första konfigurationen för dessa händelser är identisk i alla rapportsvitmallar. Händelser med s_code-variabeln N/A behöver inte anges, de tillhandahålls automatiskt.

| Commerce-evenemang av standardtyp | Typ | Variabeln `s_code` |
|---|---|---|
| Intäkter | Räknare | `purchase` |
| Beställningar | Räknare | `purchase` |
| Enheter | Räknare | `purchase` |
| Korgar | Räknare | `scOpen` |
| Vyer | Räknare | `scView` |
| Instanser | Räknare | Ej tillämpligt |
| Utcheckningar | Räknare | `scCheckout` |
| Cart Additions | Räknare | `scAdd` |
| Cart Removals | Räknare | `scRemove` |
| Besök | Räknare (inga underrelationer) | Ej tillämpligt |
| Sidvisningar | Räknare (inga underrelationer) | Ej tillämpligt |
| Dagliga unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
| Unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
