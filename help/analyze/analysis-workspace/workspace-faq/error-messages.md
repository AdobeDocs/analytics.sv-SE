---
description: Lista över felmeddelanden i Adobe Analysis Workspace och dess tillhörande komponenter
title: Vanliga felmeddelanden i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e7e03531454bd56ebe6152edc08765f42ebec728
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Vanliga felmeddelanden

Det kan uppstå fel vid interaktion med Analysis Workspace som också påverkar prestandan. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

| Felmeddelande | Varför inträffar detta? | Optimering |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss rapportserie. Medarbetare till det här felet är API-begäranden, schemalagda projekt och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för rapportsviten jämnare under hela dagen. <p>Administratörer kan använda [Rapporteringsaktivitetshanteraren för att identifiera och avbryta begäranden](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) som förbrukar rapporttapacitet. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss rapportserie. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för rapportsviten jämnare under hela dagen. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe har ett problem som måste lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe har ett problem som måste lösas. | Prova att uppdatera projektet. Om problemet kvarstår skickar du felkoden till Kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, som brandväggsinställningar [för företag](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=sv-SE), bidrar till det här felet. Dessutom kan Adobe ha ett problem som måste lösas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Segmentkriterierna eller rapportfiltret är för brett. | Begränsa sökvillkoren och försök igen. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Attribuering som inte är standard stöds inte för den dimension som du använder. | Ersätt dimensionen i tabellen med en som är kompatibel med [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |
