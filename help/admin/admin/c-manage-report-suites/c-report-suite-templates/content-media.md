---
description: Definierar vanliga inställningar för en webbplats som utvecklar ursprungligt innehåll och visar artiklar och videoklipp.
title: Innehåll och media
feature: Report Suite Settings
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 9%

---

# Innehåll och media

Definierar vanliga inställningar för en webbplats som utvecklar ursprungligt innehåll och visar artiklar och videoklipp.

| Konverteringsvariabler | Typ | Underrelationer | Allokering | Förfallotid | Variabeln `s_code` |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Commerce Variable 3 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |
| Commerce Variable 4 | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar4` |

| Success Events | Typ | Variabeln `s_code` |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| E-postregistreringar | Räknare (inga underrelationer) | `event2` |
| Prenumerationer | Räknare (inga underrelationer) | `event3` |
| Sidvisningar | Räknare (inga underrelationer) | `event4` |
| Annonsexponeringar | Räknare (inga underrelationer) | `event5` |
| Lägg till klick | Räknare (inga underrelationer) | `event6` |

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
