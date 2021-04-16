---
description: Definierar vanliga inställningar för banker och andra institutioner som ger tillgång till onlinetjänster.
title: Finansiella tjänster
feature: Administratörsverktyg
uuid: a321b409-24a4-4d9f-9aac-65761261e991
exl-id: 2ab435e2-3fc7-46f9-aee9-961f6730f3e8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 22%

---

# Finansiella tjänster

Definierar vanliga inställningar för banker och andra institutioner som ger tillgång till onlinetjänster.

| Konverteringsvariabler (eVars) | Typ | Underordnade relationer | Allokering | Förfaller | `s_code` variabel |
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
