---
description: Konfigurerar flera vanliga variabler och framgångshändelser för en vanlig webbplats.
title: Standardmall
topic: Admin tools
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Standardmall

Konfigurerar flera vanliga variabler och framgångshändelser för en vanlig webbplats.

| Konverteringsvariabler | Typ | Underrelationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Handelsvariabel 3 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |
| Handelsvariabel 4 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar4` |

| Success Events | Typ | `s_code` variabel |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| E-postregistreringar | Räknare (inga underrelationer) | `event2` |
| Prenumerationer | Räknare (inga underrelationer) | `event3` |
| Sidvyer | Räknare (inga underrelationer) | `event4` |
| Annonsexponeringar | Räknare (inga underrelationer) | `event5` |
| Lägg till klick | Räknare (inga underrelationer) | `event6` |

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

