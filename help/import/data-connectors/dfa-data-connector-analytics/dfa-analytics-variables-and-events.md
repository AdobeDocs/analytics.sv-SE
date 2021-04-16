---
description: Integreringen av Data Connectors för DFA använder Analytics-variabler för att spåra DFA-kampanjresultat.
keywords: DFA
title: Analytics-variabler och händelser
feature: Data Connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
exl-id: 8c3df2e8-84cd-4a14-b15b-42233d874c19
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# Analytics-variabler och händelser{#analytics-variables-and-events}

Integreringen av Data Connectors för DFA använder Analytics-variabler för att spåra DFA-kampanjresultat.

Förutom kampanjvariabeln kan du använda Analytics Events och eVars som passar dig. När du har identifierat händelsen och eVars som ska användas med den här DFA-integreringen använder du Analytics Admin Console för att aktivera dem. Integrationsvariablerna måste aktiveras innan DFA-integreringen aktiveras. I följande tabell beskrivs de Analytics-variabler som behövs för DFA-integreringen.

| Variabel | Eget namn | Populationsmetod | Beskrivning |
|---|---|---|---|
| s.campaign eller eVar | Annonsspårningskod | Fylls i automatiskt av Data Connector för DFA-kampanjer. | Spåra klickkonverteringar för alla kampanjer. |
| eVar* | Visa | Fylls i automatiskt via VISTA och DFA för DFA-kampanjer. | Spårar genomskinliga data för DFA ID:n. Den här eVar ska ha samma förfallodatum som variabeln *`s.campaign`*. Måste vara samma konverteringsvariabel som i variabelproviderns ID. Kontrollera att eVar har fullständiga underrelationer aktiverat. Kostnaden för att aktivera den här funktionen är en del av integreringsavgiften för Data Connectors |
| eVar* | DFA-frågefel | (Valfritt) Fylls i via JavaScript-samlingskod. | Innehåller en av flera felkoder som returnerats från DFA. |
| event* | Antal visningar | Fylls i automatiskt av Data Connector för DFA-kampanjer. | Hämtar det antal gånger som användare har visat en annons, inte klickat igenom, men kommit till din webbplats. |
| event* | Impressions | Fylls i automatiskt via en datafeed från DFA. | Spårar hur många gånger en viss DFA-annons betjänades. |
| event* | Klickningar | Fylls i automatiskt via en datafeed från DFA. | Spårar antalet gånger som användare klickat på en viss DFA-bannerannons. Detta mätresultat kan ge olika tal jämfört med det interna analysresultatet för klickfrekvens av en av flera anledningar. Mer information finns i [Avstämning av måttfel](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md). |
| event* | DFA-timeout | (Valfritt) Fylls i via JavaScript-samlingskod. | Räknar antalet gånger som DFA inte svarar innan *`s.maxDelay`*-tidsgränsen är slut. Detta kan hjälpa dig att avgöra om det finns ett DFA-implementeringsproblem. |
| event* | DFA-mediekurs | Fylls i automatiskt via en datafeed från DFA. | Innehåller de mediekursvärden som har angetts i DFA-gränssnittet. Den här funktionen måste vara aktiverad på DFA-sidan för att dessa mått ska visas. |

*Välj en oanvänd eVar eller anpassad händelse.
