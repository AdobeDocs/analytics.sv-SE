---
description: 'Läs mer om '
title: Mätvärdestyp och attribuering
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 4%

---

# Mätvärdestyp och attribuering

Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange mättyp och attribueringsmodell.

## Mätningstyp

![](assets/cm_type_alloc.png)

| Mätningstyp | Definition |
|---|---|
| Standard | Dessa mått är samma värden som används i [!DNL Analytics]-standardrapporter. Om en formel består av ett enda standardmått visas data som är identiska med den icke-beräknade metriska motsvarigheten. Standardvärden är användbara när du vill skapa beräknade värden som är specifika för varje enskilt radobjekt. Till exempel tar [Beställningar] / [Besök] order för den specifika radobjektet och dividerar den med antalet besök för den specifika radobjektet. |
| Totalt | Använd summan för rapporteringsperioden i varje radartikel. Om en formel består av ett enda totalt mätvärde visas samma totala antal på varje radartikel. Totala värden är användbara när du vill skapa beräknade värden som jämför med webbplatsens totala data. Exempel: [Beställningar] / [Totalt antal besök] visar andelen order mot ALLA besök på platsen, inte bara antalet besök för den specifika radobjektet. |

## Kolumnattributmodell

>[!IMPORTANT]
>
>[Attribution ](/help/analyze/analysis-workspace/attribution/overview.md) IQsreviderade sättet på vilket allokeringsmodeller i beräknade värden utvärderas. Som en del av denna ändring migrerades beräknade värden som använder en icke-standardallokeringsmodell till nya förbättrade attribueringsmodeller:
>
>* En fullständig lista över icke-standardattribueringsmodeller och uppslagsfönster som stöds finns i [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).
>* Allokeringsmodellerna&quot;sista beröringen i marknadsföringskanalen&quot; och&quot;Första beröringen i marknadsföringskanalen&quot; migreras till de nya attribueringsmodellerna&quot;Sista beröringen&quot; respektive&quot;Första beröringen&quot; (Obs! &quot;Marknadsföringskanaler&quot; kommer inte att bli inaktuella - bara de två allokeringsmodellerna som visas i beräknade värden kommer att vara det).
>* Dessutom kommer vi att korrigera hur linjär allokering beräknas. För kunder som använder beräknade värden med linjär allokering kan rapporterna ändras något för att återspegla den nya, korrigerade attribueringsmodellen. Den här förändringen av beräknade värden återspeglas i Analysis Workspace, Rapporter och analyser, Rapporterings-API:t och Report Builder. Mer information finns i **How Linear Allocation works (fr.o.m. 19 juli 2018**, nedan.


## Hur linjär tilldelning fungerar (från och med den 19 juli 2018)

I juli 2018 ändrade Adobe hur linjär tilldelning rapporteras för beräknade värden. Den här förändringen påverkar API:erna för Analysis Workspace, rapporter och analyser, Report Builder, Activity Map och rapportering. Ändringen påverkar i första hand eVars och andra dimensioner som är bestående. Observera att dessa ändringar endast gäller för beräknade värden och inte påverkar andra rapporter som använder linjär allokering (till exempel rapporten Sidor i Rapporter och analyser). Andra rapporter där linjär allokering används kommer även fortsättningsvis att använda den befintliga metoden för linjär allokering.

I följande exempel visas hur beräknade värden med linjär allokering kommer att ändras i rapporteringen:

|  | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 | Träff 6 | Träff 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Data skickade | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |
| eVar Sista beröring | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | 10 dollar |
| Första beröring-eVar | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | 10 dollar |
| Exempel | PROMO A | - | PROMO A | PROMO B | - | PROMO C | 10 dollar |

I det här exemplet skickades värdena A, B och C till en variabel på träffar 1, 3, 4 och 6 innan ett köp på $10 gjordes på träffnummer 7. På den andra raden kvarstår dessa värden för alla träffar på grund av senaste beröringsbesök. Den tredje raden visar hur obestridliga besöken är. Slutligen visar den sista raden hur data skulle registreras för en prop som inte är beständig.

## Skillnader i hur linjär allokering fungerar i rapporter och analyser jämfört med arbetsytan

Det finns vissa skillnader i hur linjär attribuering fungerar mellan dessa två verktyg:

* I Rapporter och analyser är (bearbetad) linjär attribuering alltid besöksbaserad, medan den i Workspace kan vara besöks- eller besöksbaserad.
* Om inget värde skickades vid den första besöksträffen i Rapporter och analyser kvarstår (det inledande) värdet från föregående besök. Detta är INTE fallet i Workspace (Attribution IQ). Om inget värde skickas vid den första besöksträffen är &quot;Inget&quot; det ursprungliga värdet.

## Hur linjär tilldelning fungerade före juli 2018

Före den 19 juli 2018 beräknades linjär attribuering efter att en första beröring eller sista beröringspartiklar redan hade gjorts. Detta innebar att för den sista beröringsdelen ovan skulle eVar $10 fördelas enligt följande: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

För den första touch-eVar ovan ges A alla 10 dollar. För propen: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 och C = 10 * (1/4) = $2,50. Så här sammanfattar du linjär allokering som den fungerade tidigare:

| Värden | Aktuell eVar för senaste beröring | Aktuell eVar med första beröring | Aktuellt uttryck |
|---|---|---|---|
| PROMO A | 5,00 USD | 10.00 USD | 5,00 USD |
| PROMO B | 3,33 USD | $0 | 2,50 USD |
| PROMO C | $1,67 | $0 | 2,50 USD |
| Totalt | 10.00 USD | 10.00 USD | 10.00 USD |

**Sammanfattning av hur linjär allokering fungerar nu**

I stället för att använda de beständiga värden som baseras på senaste beröring eller första beröring använder [!DNL Analytics] nu bara de värden som skickades (den första raden i den övre tabellen). Inställningarna för dimensionsallokering påverkar inte längre det sätt på vilket linjär allokering beräknas (vilket innebär att props och eVars behandlas på samma sätt), och resultaten avspeglar det som ursprungligen skickades i stället för det första eller sista beröringsvärdet som kan ha varit bestående. I alla tre fallen är alltså A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 och C = 10 * (1/4) = $2,50.

| Värden | Ny eVar för senaste beröring | Ny eVar med första beröring | Nytt utkast |
|---|---|---|---|
| PROMO A | 5,00 USD | 5,00 USD | 5,00 USD |
| PROMO B | 2,50 USD | 2,50 USD | 2,50 USD |
| PROMO C | 2,50 USD | 2,50 USD | 2,50 USD |
| Totalt | 10.00 USD | 10.00 USD | 10.00 USD |
