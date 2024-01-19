---
description: Läs mer om
title: Mättyp och attribuering
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Mättyp och attribuering

När [bygga ett beräknat mätvärde](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)kan du ange måtttyp och attribueringsmodell.

## Mätningstyp

Så här anger du måtttypen när du skapar ett beräknat mått:

1. Markera kugghjulsikonen bredvid mätvärdet vars typ du vill markera.

   ![](assets/cm_type_alloc.png)

1. Välj bland följande alternativ:

   | Mätningstyp | Definition |
   |---|---|
   | Standard | Dessa mått är samma som de som används i standard [!DNL Analytics] rapportering. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel: [Beställningar] / [Besök] tar emot order för den specifika radartikeln och dividerar den med antalet besök för den specifika radartikeln. |
   | Summa | Använd totalsumma för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalmått visas samma totaltal på varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Till exempel: [Beställningar] / [Totalt antal besök] visar hur stor andel av beställningarna som gäller för ALLA besök på er webbplats, inte bara besöken till den specifika radobjektet. |

## Så här fungerar linjär allokering

[Attribut](/help/analyze/analysis-workspace/attribution/overview.md) är hur allokeringsmodeller i beräknade värden utvärderas.

En fullständig lista över icke-standardattribueringsmodeller och uppslagsfönster som stöds finns i [Attributmodeller och uppslagsfönster](/help/analyze/analysis-workspace/attribution/models.md).

I följande exempel visas hur beräknade mätvärden med linjära tilldelningar fungerar vid rapportering:

| | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 | Träff 6 | Träff 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Data skickade | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |
| EVar vid senaste beröring | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | 10 dollar |
| EVar med första beröring | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | 10 dollar |
| Exempel | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |

I det här exemplet skickades värdena A, B och C till en variabel på träffar 1, 3, 4 och 6 innan ett köp på $10 gjordes på träffnummer 7. På den andra raden kvarstår dessa värden för alla träffar på grund av senaste beröringsbesök. Den tredje raden visar hur obestridliga besöken är. Slutligen visar den sista raden hur data skulle registreras för en prop som inte är beständig.

