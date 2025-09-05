---
title: AM/PM
description: Fastställer om träffen inträffade under AM- eller PM-timmar.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

---

# AM/PM

AM/PM [dimension](overview.md) ger information om huruvida träffen inträffade under AM- eller PM-timmar. Tid för träffen baseras på [rapportsvitens tidszon](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska. Den har inga inställningar att ändra. Dess enda beroende är av rapportsvitens tidszon, som avgör vilka timmar som är AM och vilka som är PM.

## Dimension-objekt

Den här dimensionen innehåller alltid exakt två dimensionsobjekt: `"AM"` och `"PM"`. Dimensionsobjektet `"AM"` gäller för alla träffar från 12:00 AM till 11:59 AM, medan dimensionsobjektet `"PM"` gäller för alla träffar från 12:00 PM till 11 :59 PM.
