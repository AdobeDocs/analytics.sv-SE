---
description: Lista över felmeddelanden i Adobe Analysis Workspace och dess tillhörande komponenter
title: Vanliga felmeddelanden i Analysis Workspace
translation-type: tm+mt
source-git-commit: 1df7eb2b8734a7c260f843494c414a927638ebb4
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---


# Vanliga felmeddelanden

Det kan uppstå fel vid interaktion med Analysis Workspace som också påverkar prestandan. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

| Felmeddelande | Varför inträffar detta? | Optimering |
| --- | --- | --- |
| Ett systemfel har inträffat. Logga en kundtjänstförfrågan under Hjälp > Skicka supportanmälan och ange din felkod. | Adobe har ett problem som måste lösas. | Skicka felkoden till kundtjänst. |
| Fel 500: Det gick inte att läsa in sidan | Problem med ditt lokala nätverk, t.ex. brandväggsinställningar [](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html), bidrar till det här felet. Dessutom kan Adobe ha ett problem som måste lösas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| Ett av segmenten eller sökningen i den här visualiseringen innehåller en textsökning som returnerade för många resultat. | Segmentkriterierna eller rapportfiltret är för brett. | Begränsa sökvillkoren och försök igen. |
| Rapporteringssviten är ovanligt tung. Försök igen senare. | Din organisation försöker köra för många samtidiga begäranden mot en viss rapportserie. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för rapportsviten jämnare under hela dagen. |
| Begäran är för komplex. | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av begärans storlek, för många matchade objekt i ett segment eller sökfilter, för många mätvärden, inkompatibla mått- och mätkombinationer osv. | Förenkla begäran genom att ta bort vissa kolumner eller rader i tabellen, eller dela upp tabellen i separata begäranden. |
| Den här dimensionen stöder för närvarande inte icke-standardattribueringsmodeller. | Attribuering som inte är standard stöds inte för den dimension som du använder. | Ersätt dimensionen i tabellen med en som är kompatibel med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| Din begäran misslyckades på grund av för många kolumner eller förkonfigurerade rader. | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |
