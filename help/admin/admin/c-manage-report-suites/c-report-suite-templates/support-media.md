---
description: Innehåller vanliga inställningar för en webbplats som innehåller artiklar och videor om produktsupport.
title: Supportmedia
feature: Report Suite Settings
exl-id: f522173a-8f58-4fa4-868b-251158a71e26
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 21%

---

# Supportmedia

Innehåller vanliga inställningar för en webbplats som innehåller artiklar och videor om produktsupport.

| Konverteringsvariabler | Typ | Underordnade relationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar2` |
| Självbetjäningshändelsetyp | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar3` |

Inga lyckade händelser har konfigurerats av den här rapportsvitmallen.

| Custom Insight Variables | `s_code` variabel |
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
| Kundvagnsvisningar | Räknare | `scView` |
| Instanser | Räknare | Ej tillämpligt |
| Utcheckningar | Räknare | `scCheckout` |
| Tillägg i kundvagn | Räknare | `scAdd` |
| Raderingar i kundvagn | Räknare | `scRemove` |
| Besök | Räknare (inga underrelationer) | Ej tillämpligt |
| Sidvisningar | Räknare (inga underrelationer) | Ej tillämpligt |
| Dagliga unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
| Unika besökare | Räknare (inga underrelationer) | Ej tillämpligt |
