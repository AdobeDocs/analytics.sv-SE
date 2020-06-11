---
title: AM/PM
description: Fastställer om träffen inträffade under AM- eller PM-timmar.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---


# AM/PM

Dimensionen AM/PM ger insikter om huruvida träffen inträffade under AM- eller PM-timmar. Tidpunkten för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska. Den har inga inställningar att ändra. Dess enda beroende är av rapportsvitens tidszon, som avgör vilka timmar som är AM och vilka som är PM.

## Dimensionsvärden

Den här dimensionen innehåller alltid exakt två dimensionsvärden: `"AM"` och `"PM"`. Dimensionsvärdet `"AM"` gäller för alla träffar från 12:00 till 11:59, medan dimensionsvärdet `"PM"` gäller för alla träffar från 12:00 till 11:59.
