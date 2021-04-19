---
description: Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.
keywords: Datafeed;jobb;mått;förkolumn;efterkolumn;bots;datumfiltrering;händelsesträng;vanliga;formler
title: Beräkna mätvärden
feature: Rapporter och analyser - Grunderna och analyser
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# Använd dataflöden för att beräkna gemensamma mätvärden

Beskriver hur man beräknar vanliga mätvärden med hjälp av dataflöden.

>[!IMPORTANT]
>
>Träffar som normalt inte ingår i Adobe Analytics ingår i dataflöden. Använd `exclude_hit > 0` för att ta bort uteslutna träffar från frågor om rådata. Data som samlats in ingår också i dataflöden. Om du vill utesluta datakällor ska du exkludera alla rader med `hit_source = 5,7,8,9`.

## Sidvyer

1. Räkna antalet rader där ett värde är i `post_pagename` eller `post_page_url`.

## Besök

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num` och `visit_start_time_gmt`.
1. Räkna det unika antalet värden.

>[!NOTE]
>
>Internet-oegentligheter, systemoegentligheter eller användning av anpassade besökar-ID:n kan sällan använda samma `visit_num`-värden för olika besök. Använd `visit_start_time_gmt` vid inventering av besök för att se till att dessa besök räknas.

## Besökare

Alla metoder som Adobe använder för att identifiera unika besökare (anpassat besökar-ID, Experience Cloud ID-tjänst osv.) beräknas som ett värde i `post_visid_high` och `post_visid_low`. Sammanfogningen av dessa två kolumner kan användas som standard för att identifiera unika besökare oavsett hur de identifierades som en unik besökare. Om du vill veta vilken metod Adobe som används för att identifiera en unik besökare använder du kolumnen `post_visid_type`.

1. Sammanfoga `post_visid_high` och `post_visid_low`.
2. Räkna det unika antalet värden.

## Anpassade länkar, nedladdningslänkar och avslutande länkar

1. Räkna antalet rader där:
   * `post_page_event = 100` för anpassade länkar
   * `post_page_event = 101` för nedladdningslänkar
   * `post_page_event = 102` för slutlänkar

## Anpassade händelser

Alla mått räknas som kommaavgränsade heltal i kolumnen `post_event_list`. Använd `event.tsv` för att matcha numeriska värden med önskad händelse. `post_event_list = 1,200` indikerar till exempel att träffen innehöll en köphändelse och en anpassad händelse, 1.

1. Antal gånger som värdet för händelsesökning visas i `post_event_list`.

## Tid

Träffarna måste först grupperas efter besök och sedan sorteras efter träffnumret på besöket.

1. Sammanfoga `post_visid_high`, `post_visid_low`, `visit_num` och `visit_start_time_gmt`.
2. Sortera efter det här sammanfogade värdet och tillämpa sedan en andra sortering med `visit_page_num`.
3. Om en träff inte är den sista vid ett besök kan du subtrahera `post_cust_hit_time`-värdet från den efterföljande träffens `post_cust_hit_time`-värde.
4. Detta är den tid (i sekunder) som träffen tar. Filter kan användas för att fokusera på dimensionsobjekt eller händelser.

## Beställningar, enheter och intäkter

Om ett träffvärde `currency` inte matchar en rapportsvits valuta, konverteras det med den dagens konverteringsgrad. Kolumnen `post_product_list` använder det konverterade valutavärdet, så alla träffar använder samma valuta i den här kolumnen.

1. Uteslut alla rader där `duplicate_purchase = 1`.
2. Inkludera endast rader där `event_list` innehåller inköpshändelsen.
3. Tolka `post_product_list`-kolumnen för att extrahera alla prisdata. Kolumnen `post_product_list` är formaterad på samma sätt som variabeln `s.products`.
4. Beräkna det önskade måttet:
   * Räkna antalet rader för att beräkna order
   * Summera antalet `quantity` i produktsträngen för beräkning av enheter
   * Summa antalet `price` i produktsträngen för att beräkna intäkt
