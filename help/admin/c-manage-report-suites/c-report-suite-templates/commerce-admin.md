---
description: Definierar vanliga inställningar för en e-handelswebbplats.
title: Handel
topic: Admin tools
uuid: 85fc235d-0180-4245-b831-0243ebe3c40c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Handel

Definierar vanliga inställningar för en e-handelswebbplats.

| Konverteringsvariabler | Typ | Underrelationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Interna kampanjer | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Marknadsföringskategori | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |
| Handelsvariabel 4 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar4` |
| Handelsvariabel 5 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar5` |

| Success Events | Typ | `s_code` variabel |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| Anpassade händelser 1-5 | Räknare (inga underrelationer) | `event1, event2, event3, event4, event5` |

| Anpassade insiktsvariabler | `s_code` variabel |
|---|---|
| Trafikegenskap 1-5 | `prop1, prop2, prop3, prop4, prop5` |

Följande tabell innehåller en lista med standardhändelser för e-handel. Den första konfigurationen för dessa händelser är identisk i alla rapportsvitmallar. Händelser med s_code-variabeln N/A behöver inte anges, de tillhandahålls automatiskt.

| Standardhandelshändelser | Typ | `s_code` variabel |
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
| Sidvyer | Räknare (inga underrelationer) | Ej tillämpligt |
| Dagliga unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
| Unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |

