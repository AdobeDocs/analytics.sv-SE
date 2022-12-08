---
description: Definierar vanliga inställningar för en webbplats som samlar innehåll, till exempel en nyhetsportal.
title: Aggregatorportal
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 21%

---

# Aggregatorportal

Definierar vanliga inställningar för en webbplats som samlar innehåll, till exempel en nyhetsportal.

| Konverteringsvariabler | Typ | Underordnade relationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar2` |
| Referenskategori | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar3` |

| Success Events | Typ | `s_code` variabel |
|---|---|---|
| Logga in | Räknare (inga underrelationer) | `event1` |
| Referensvy | Räknare (inga underrelationer) | `event2` |
| Referensklickningar | Räknare (inga underrelationer) | `event3` |

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
