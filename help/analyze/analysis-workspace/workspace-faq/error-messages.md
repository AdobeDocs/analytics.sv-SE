---
description: Läs mer om fel och felsökning för Analysis Workspace.
title: Fel och felsökning
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 11%

---

# Fel och felsökning

Det kan uppstå fel vid interaktion med Analysis Workspace som kan påverka dess funktioner eller prestanda. Nedan visas de vanligaste feltyperna, varför de inträffar och optimeringar som kan göras.

## Felmeddelanden

Några vanliga felmeddelanden du kan se när du använder Analysis Workspace:

| Felmeddelande | Varför inträffar felet? | Optimering |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt, schemalagda rapporter, schemalagda aviseringar och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen.<p>Administratörer kan använda [Rapporteringsaktivitetshanteraren för att identifiera och avbryta begäranden](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) som förbrukar rapporttapacitet.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | Din rapporteringsbegäran är för stor och kan inte utföras. Medarbetare till det här felet är timeout på grund av att begäran är komplex. | Förenkla er begäran. Du kan t.ex. korta ned datumintervallet, förenkla segmentvillkoren eller ta bort vissa kolumner eller rader i tabellen. Du kan också dela upp tabellen i separata begäranden. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | Din organisation försöker köra för många samtidiga begäranden mot en viss datavy. Medarbetare till det här felet är API-begäranden, schemalagda projekt och samtidiga användare som gör rapporteringsförfrågningar. | Sprid era förfrågningar och scheman för datavyn jämnare under dagen. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe har ett problem som behöver lösas. | Skicka felkoden till kundtjänst. |
| [!UICONTROL Error 500: Failed to load page] | Problem med ditt lokala nätverk, som brandväggsinställningar [för företag](/help/technotes/ip-addresses.md), bidrar till det här felet. Dessutom kan Adobe ha problem som behöver åtgärdas. | Försök logga in igen efter flera minuter. Om problemet kvarstår skickar du EIM-instans-ID-koden till Kundtjänst. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Tabellen innehåller för många frihandsceller (rad * kolumner). | Ta bort kolumner eller rader i tabellen eller dela upp tabellen i separata begäranden. |


## Felsökning

När du använder Analysis Workspace kan du använda informationen nedan för att felsöka några vanliga problem.

| Problem | Felsöka |
|---|---|
| När jag drar ett mätresultat över står det *Ogiltiga data*. | Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida. |
| När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor. | Om du har skapat en rapport om arbetsytan men det inte finns några data kan du kontrollera några saker:<ul><li>Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.</li><li>Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.</li><li>Navigera till webbplatsen och använd [Felsökning](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=sv-SE) för att verifiera att data samlas in.</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=sv-SE), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->