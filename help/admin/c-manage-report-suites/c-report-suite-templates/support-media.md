---
description: Innehåller vanliga inställningar för en webbplats som innehåller artiklar och videor om produktsupport.
title: Support Media
topic: Admin tools
uuid: 6072f14c-a67d-470c-b977-c18e26e901db
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Support Media

Innehåller vanliga inställningar för en webbplats som innehåller artiklar och videor om produktsupport.

| Konverteringsvariabler | Typ | Underrelationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Självbetjäningshändelsetyp | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |

Inga lyckade händelser har konfigurerats av den här rapportsvitmallen.

| Anpassade insiktsvariabler | `s_code` variabel |
|---|---|
| Säker/ej säker | `prop1` |
| Trafikegenskap 2-5 | `prop2, prop3, prop4, prop5` |

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

