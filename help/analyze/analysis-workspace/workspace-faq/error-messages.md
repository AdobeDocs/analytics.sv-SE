---
description: Lista över felmeddelanden i Adobe Analysis Workspace och dess tillhörande komponenter
title: Vanliga felmeddelanden i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# Vanliga felmeddelanden

Det kan uppstå fel vid interaktion med Analysis Workspace som också påverkar prestandan. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

| Felmeddelande | Varför inträffar detta? | Optimering |
| --- | --- | --- |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe har ett problem som måste lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe har ett problem som måste lösas. | Prova att uppdatera projektet. Om problemet kvarstår skickar du felkoden till Kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, till exempel företag [brandväggsinställningar](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), är en bidragande faktor till det här felet. Dessutom kan Adobe ha ett problem som måste lösas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Segmentkriterierna eller rapportfiltret är för brett. | Begränsa sökvillkoren och försök igen. |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss rapportserie. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för rapportsviten jämnare under hela dagen. |
| [!UICONTROL The request is too complex.] | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av begärans storlek, för många matchade objekt i ett segment eller sökfilter, för många mätvärden, inkompatibla mått- och mätkombinationer osv. | Förenkla begäran genom att ta bort vissa kolumner eller rader i tabellen, eller dela upp tabellen i separata begäranden. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Attribuering som inte är standard stöds inte för den dimension som du använder. | Ersätt dimensionen i tabellen med en som är kompatibel med [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |
