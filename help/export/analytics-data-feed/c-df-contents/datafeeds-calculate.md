---
description: Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: Beräkna mått
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Använd dataflöden för att beräkna gemensamma mätvärden

Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.

> [!IMPORTANT] Träffar som normalt inte ingår i Adobe Analytics ingår i dataflödena. Använd `exclude_hit > 0` för att ta bort uteslutna träffar från frågor om rådata. Data som samlats in ingår också i dataflöden. Om du vill utesluta datakällor ska du exkludera alla rader med `hit_source = 5,7,8,9`.

## Sidvyer

1. Räkna antalet rader där ett värde finns i `post_pagename` eller `post_page_url`.

## Besök

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num`och `visit_start_time_gmt`.
1. Räkna det unika antalet värden.

> [!NOTE] Internets oegentligheter, systemoegentligheter eller användning av anpassade besökar-ID:n kan sällan använda samma `visit_num` värden för olika besök. Använd `visit_start_time_gmt` när du räknar besök för att se till att dessa besök räknas.

## Besökare

Alla metoder som Adobe använder för att identifiera unika besökare (anpassat besökar-ID, Experience Cloud ID-tjänst osv.) beräknas som ett värde i `post_visid_high` och `post_visid_low`. Sammanfogningen av dessa två kolumner kan användas som standard för att identifiera unika besökare oavsett hur de identifierades som en unik besökare. Om du vill veta vilken metod Adobe använde för att identifiera en unik besökare använder du kolumnen `post_visid_type`.

1. Sammanfoga `post_visid_high` och `post_visid_low`.
2. Räkna det unika antalet värden.

## Anpassade länkar, nedladdningslänkar och avslutande länkar

1. Räkna antalet rader där:
   * `post_page_event = 100` för anpassade länkar
   * `post_page_event = 101` för nedladdningslänkar
   * `post_page_event = 102` för slutlänkar

## Anpassade händelser

Alla mätvärden räknas som kommaavgränsade heltal i kolumnen `post_event_list` . Använd `event.tsv` för att matcha numeriska värden med önskad händelse. Anger till exempel `post_event_list = 1,200` att träffen innehöll en köphändelse och en anpassad händelse 1.

1. Antal gånger som värdet för händelsesökning visas i `post_event_list`.

## Tid

Träffarna måste först grupperas efter besök och sedan sorteras efter träffnumret på besöket.

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num`och `visit_start_time_gmt`.
2. Sortera efter det här sammanfogade värdet och använd sedan en andra sortering efter `visit_page_num`.
3. Om en träff inte är den sista vid ett besök tar du bort `post_cust_hit_time` värdet från den efterföljande träffens `post_cust_hit_time` värde.
4. Detta är den tid (i sekunder) som träffen tar. Filter kan användas för att fokusera på dimensionsvärden och händelser.

## Beställningar, enheter och intäkter

Om en träds `currency` värde inte matchar rapportsvitens valuta, konverteras det med den dagens konverteringsgrad. Kolumnen `post_product_list` använder det konverterade valutavärdet, så alla träffar använder samma valuta i den här kolumnen.

1. Uteslut alla rader där `duplicate_purchase = 1`.
2. Inkludera endast rader där `event_list` innehåller inköpshändelsen.
3. Tolka kolumnen för att extrahera alla prisdata `post_product_list` . Kolumnen `post_product_list` formateras på samma sätt som `s.products` variabeln.
4. Beräkna det önskade måttet:
   * Räkna antalet rader för att beräkna order
   * Summera antalet `quantity` i produktsträngen som enheter ska beräknas på
   * Summa antalet `price` i produktsträngen som intäkten ska beräknas på
