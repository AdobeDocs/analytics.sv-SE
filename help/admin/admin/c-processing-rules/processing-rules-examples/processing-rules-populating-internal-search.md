---
description: Om du använder en vanlig variabel, t.ex. q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVar-satsen för de interna söktermerna med dessa värden.
subtopic: Processing rules
title: Fylla i interna söktermer med en frågesträngsparameter
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fylla i interna söktermer med en frågesträngsparameter

Om du använder en vanlig variabel, t.ex. q, för att fylla i söktermer, kan du använda bearbetningsregler för att fylla i eVar-satsen för de interna söktermerna med dessa värden.

Frågesträngsvärden måste kodas i Unicode eller UTF-8 för att kunna läsas av bearbetningsregler.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om frågesträngsparametern q har angetts |
| Åtgärd | Skriv över värdet för interna söktermer till frågesträngsparameter q |

Exempel:

![](assets/populate-internal-search-terms.png)

