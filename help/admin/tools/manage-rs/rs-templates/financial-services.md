---
description: Definierar vanliga inställningar för banker och andra institutioner som ger tillgång till onlinetjänster.
title: Finansiella tjänster
feature: Report Suite Settings
exl-id: 2ab435e2-3fc7-46f9-aee9-961f6730f3e8
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 9%

---

# Finansiella tjänster

Definierar vanliga inställningar för banker och andra institutioner som ger tillgång till onlinetjänster.

| Konverteringsvariabler (eVars) | Typ | Underrelationer | Allokering | Förfallotid | Variabeln `s_code` |
|---|---|---|---|---|---|
| Intern kampanj | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar1` |
| Interna sökvillkor | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar2` |
| Självbetjäningshändelsetyp | Sträng | Grundläggande | Senaste (senaste) | Besök | `evar3` |

Inga lyckade händelser har konfigurerats av den här rapportsvitmallen.

| Custom Insight Variables | Variabeln `s_code` |
|---|---|
| Säker/ej säker | `prop1` |
| Trafikegenskap 2-5 | `prop2, prop3, prop4, prop5` |

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
