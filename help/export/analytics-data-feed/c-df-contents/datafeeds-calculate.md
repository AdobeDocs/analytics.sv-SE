---
description: Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.
keywords: Datafeed;jobb;mått;förkolumn;efterkolumn;bots;datumfiltrering;händelsesträng;vanliga;formler
title: Beräkna mått
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Använd dataflöden för att beräkna gemensamma mätvärden

Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.

>[!NOTE]
>
>Träffar som normalt inte ingår i Analysis Workspace ingår i dataflöden. Du kan lägga till följande villkor i dina frågor om de är relevanta:
>
>* **`exclude_hit`**: Analysis Workspace innehåller endast data där `exclude_hit = 0`.
>* **`customer_perspective`**: Analysis Workspace innehåller bara data där `customer_perspective = 0`, såvida du inte använder en virtuell rapportsvit som innehåller mobila bakgrundstötlar.
>* **`hit_source`**: Data från datakällor kan innehålla skillnader mellan rådata och Analysis Workspace. Om du vill exkludera träffar från datakällor ska du exkludera alla rader där `hit_source = 5,7,8,9`.

## Sidvyer

1. Räkna antalet rader där ett värde finns i `post_pagename` eller `post_page_url`.

## Förekomster

1. Räkna det totala antalet rader.

## Besök

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num` och `visit_start_time_gmt`.
1. Räkna det unika antalet värden.

>[!TIP]
>
>Internet-oegentligheter, systemoegentligheter eller användning av anpassade besökar-ID:n kan sällan använda samma `visit_num`-värden för olika besök. Använd `visit_start_time_gmt` när du räknar besök, även om det är valfritt, för att se till att dessa besök räknas.

## Besökare

Alla metoder som Adobe använder för att identifiera unika besökare (anpassat besökar-ID, Experience Cloud ID-tjänst osv.) beräknas som ett värde i `post_visid_high` och `post_visid_low`. Sammanfogningen av dessa två kolumner kan användas som standard för att identifiera unika besökare oavsett hur de identifierades som en unik besökare. Om du vill veta vilken metod Adobe använde för att identifiera en unik besökare använder du kolumnen `post_visid_type`.

1. Sammanfoga `post_visid_high` och `post_visid_low`.
2. Räkna det unika antalet värden.

## Anpassade länkar, nedladdningslänkar och avslutande länkar

1. Antal rader där:
   * `post_page_event = 100` för anpassade länkar
   * `post_page_event = 101` för nedladdningslänkar
   * `post_page_event = 102` för avslutslänkar

## Anpassade händelser

Alla mått räknas i kolumnen `post_event_list` som kommaavgränsade heltal. Använd `event.tsv` om du vill matcha numeriska värden med den önskade händelsen. `post_event_list = 1,200` indikerar till exempel att träffen innehöll en köphändelse och en anpassad händelse, 1.

1. Antal gånger som värdet för händelsesökning visas i `post_event_list`.

## Tidsåtgång

Träffarna måste först grupperas efter besök och sedan beställas enligt träffnumret.

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num` och `visit_start_time_gmt`.
2. Sortera efter det här sammanfogade värdet och tillämpa sedan en andra sortering efter `visit_page_num`.
3. Om en träff inte är den sista i ett besök drar du av värdet `post_cust_hit_time` från den efterföljande träffens `post_cust_hit_time`-värde.
4. Detta är den tid (i sekunder) som träffen tar. Filter kan användas för att fokusera på dimensionsobjekt eller händelser.

## Beställningar, enheter och intäkter

Om en träffs `currency`-värde inte matchar en rapportsvits valuta, konverteras det med den dagens konverteringsgrad. Kolumnen `post_product_list` använder det konverterade valutavärdet, så alla träffar använder samma valuta i den här kolumnen.

1. Uteslut alla rader där `duplicate_purchase = 1`.
2. Inkludera endast rader där `event_list` innehåller inköpshändelsen.
3. Tolka kolumnen `post_product_list` för att extrahera alla prisdata. Kolumnen `post_product_list` har samma format som variabeln `s.products`.
4. Beräkna det önskade måttet:
   * Räkna antalet rader för att beräkna order
   * Summera antalet `quantity` i produktsträngen för att beräkna enheter
   * Summa antalet `price` i produktsträngen för att beräkna intäkt
