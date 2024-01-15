---
description: Om du använder en vanlig variabel, till exempel q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVarna för interna sökvillkor med dessa värden.
subtopic: Processing rules
title: Fylla i interna söktermer med en frågesträngsparameter
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 1%

---

# Fylla i interna söktermer med en frågesträngsparameter

Om du använder en vanlig variabel, till exempel q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVarna för interna sökvillkor med dessa värden.

Frågesträngsvärden måste kodas i Unicode eller UTF-8 för att kunna läsas av bearbetningsregler.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om frågesträngsparametern q har angetts |
| Åtgärd | Skriv över värdet för interna söktermer till frågesträngsparameter q |

Exempel:

![](assets/populate-internal-search-terms.png)
