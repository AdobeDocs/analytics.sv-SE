---
description: Om du använder en vanlig variabel, till exempel q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVar för interna söktermer med dessa värden.
subtopic: Processing rules
title: Fylla i interna söktermer med en frågesträngsparameter
feature: Administratörsverktyg
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%

---

# Fylla i interna söktermer med en frågesträngsparameter

Om du använder en vanlig variabel, till exempel q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVar för interna söktermer med dessa värden.

Frågesträngsvärden måste kodas i Unicode eller UTF-8 för att kunna läsas av bearbetningsregler.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om frågesträngsparametern q har angetts |
| Åtgärd | Skriv över värdet för interna söktermer till frågesträngsparameter q |

Exempel:

![](assets/populate-internal-search-terms.png)
