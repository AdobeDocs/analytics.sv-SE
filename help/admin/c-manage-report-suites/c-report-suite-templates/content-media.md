---
description: Definierar vanliga inställningar för en webbplats som utvecklar ursprungligt innehåll och visar artiklar och videoklipp.
title: Innehåll och media
feature: Administratörsverktyg
uuid: 281b0bf8-59dc-46dc-b5d5-5e42827b785d
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 21%

---

# Innehåll och media

Definierar vanliga inställningar för en webbplats som utvecklar ursprungligt innehåll och visar artiklar och videoklipp.

| Konverteringsvariabler | Typ | Underordnade relationer | Allokering | Förfaller | `s_code` variabel |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar2` |
| Handelsvariabel 3 | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar3` |
| Handelsvariabel 4 | Sträng | Grundläggande | Senaste (senaste) | Gå in på | `evar4` |

| Success Events | Typ | `s_code` variabel |
|---|---|---|
| Registreringar | Räknare (inga underrelationer) | `event1` |
| E-postregistreringar | Räknare (inga underrelationer) | `event2` |
| Prenumerationer | Räknare (inga underrelationer) | `event3` |
| Sidvisningar | Räknare (inga underrelationer) | `event4` |
| Annonsexponeringar | Räknare (inga underrelationer) | `event5` |
| Lägg till klick | Räknare (inga underrelationer) | `event6` |

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
