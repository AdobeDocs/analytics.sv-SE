---
title: AM/PM
description: Fastställer om träffen inträffade under AM- eller PM-timmar.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# AM/PM

FM/PM [dimension](overview.md) ger insikter om huruvida träffen inträffade under AM- eller PM-timmar. Tid för träffen baseras på [rapportsvitens tidszon](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska. Den har inga inställningar att ändra. Dess enda beroende är av rapportsvitens tidszon, som avgör vilka timmar som är AM och vilka som är PM.

## Dimensioner

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"AM"` och `"PM"`. Dimensionsartikeln `"AM"` gäller för alla träffar från 12:00 till 11:59, medan dimensionsobjektet `"PM"` gäller för alla träffar från 12:00 till 11:59.
