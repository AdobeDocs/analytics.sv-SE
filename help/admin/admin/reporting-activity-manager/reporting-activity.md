---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 0e03379550808e5be3e86f0f9ddbbedd026d4910
workflow-type: tm+mt
source-wordcount: '1564'
ht-degree: 1%

---

# Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] gör det möjligt för administratörer att snabbt diagnostisera och åtgärda problem med rapporttapaciteten under perioder med hög rapporteringsnivå.

Mer information om Reporting Activity Manager, inklusive viktiga fördelar och behörighetskrav, finns i [Översikt över Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Visa rapporteringsaktivitet för alla rapportsviter {#view-all-report-suites}

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

   En lista över dina aktiverade basrapportsviter visas.

   ![rapportkö](/help/admin/admin/assets/reporting-activity1.png)

1. (Valfritt) Du kan söka efter eller filtrera listan med rapportsviter:

   * Använd sökfältet för att söka efter en specifik rapportsserie. Börja skriva rapportsvitens namn eller ID och listan över rapportsviter uppdateras medan du skriver.

   * Välj [!UICONTROL **Filter**] icon ![Filterikon](assets/filter-icon.png) om du vill expandera listan med filteralternativ. Du kan filtrera efter [!UICONTROL **Favoriter**] eller [!UICONTROL **Status**].

     Om du vill markera en rapportserie som favorit väljer du stjärnikonen till vänster om rapportsvitens namn.

<!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Visa användningsinformation om varje rapportserie. Du kan välja en kolumnrubrik för att sortera tabellen efter den kolumnen.

   Följande kolumner är tillgängliga:

   | Gränssnittselement | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Report Suite]** | Basrapportsviten vars rapporteringsaktivitet du övervakar. |
   | **[!UICONTROL Virtual report suites]** | Visar alla virtuella rapportsviter som matas in i denna basrapportsserie. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla förfrågningar som kommer från de virtuella rapportsviterna kombineras och kommer ned till basrapportsviten.<p>Om du till exempel har 10 begäranden från 5 VRS är det 50 förfrågningar från rapportsviten på basnivå. På så sätt kan du snabbt nå ut till din kapacitet. |
   | **[!UICONTROL Capacity utilization]** | Procentandelen av rapportsvitens rapporteringskapacitet som används i realtid. <p>**Anteckning** Även om användarkapaciteten är 100 % behöver det inte innebära att du bör avbryta rapporteringsbegäranden. 100 % användningskapacitet kan vara hälsosam om den genomsnittliga väntetiden är rimlig. 100 % användningskapacitet kan tyda på ett problem om antalet begäranden i kö också ökar.</p> |
   | **[!UICONTROL Queued requests]** | Antalet begäranden som väntar på att behandlas. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | Genomsnittlig väntetid för varje begäran som ska behandlas. <!-- ???? --> |
   | **[!UICONTROL Status]** | Möjliga statusvärden är: <ul><li>[!UICONTROL **Aktiv**] (blått): Rapporter har körts på rapportsviten och den övervakas för aktivitet.</li><li>[!UICONTROL **Inaktiv**] (grå): Inga rapporter har någonsin körts för rapportsviten. Den här statusen visas endast när rapportsviter skapas.</li></ul> |

   {style="table-layout:auto"}

## Visa rapporteringsaktivitet för en enskild rapportserie

1. I Adobe Analytics: [!UICONTROL **Administratör**] > [!UICONTROL **Rapporteringsaktivitetshanteraren**].

1. Markera den länkade titeln för den rapportsserie som du vill visa information om.

   Rapporteringsaktivitetsdata visas för den rapportserie som du har valt.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. Använd tillgängliga diagram och tabeller för att förstå rapporteringsaktiviteten i rapportsviten.

   * [Visa diagram](#view-graphs)

   * [Visa register](#view-data-in-the-table)

### Visa diagram

Följande diagram är tillgängliga för att hjälpa dig att bättre förstå vad som händer i rapportsviten. Om diagrammen inte visas markerar du [!UICONTROL **Visa diagram**] -knappen.

#### Användningsdiagram {#utilization}

Diagrammet visar hur rapporteringsanvändningen för den valda rapportsviten har använts under de senaste två timmarna.

* X-axeln visar den rapporterade användningskapaciteten under de senaste två timmarna.
* Y-axeln visar procentandelen av rapportanvändningskapacitet, per minut.
* Du kan hovra över diagrammet för att visa tidpunkter där procentandelen av användningskapaciteten var högst för den minuten.

  ![utnyttjandediagram](assets/utilization-graph.png)

#### Diagram över distinkta användare

Diagrammet Distinkta användare visar rapporteringsaktiviteten för den valda rapportsviten under de senaste två timmarna.

* X-axeln visar en 2-timmars tidsram.
* Y-axeln visar antalet användare som har gjort rapportförfrågningar, per minut.
* Du kan hålla pekaren över diagrammet för att visa tidpunkter där det högsta antalet användare var under den minuten.

  ![Diagram över distinkta användare](assets/distinct-users-graph.png)

<!--

#### Requests graph

The Requests graph shows the number of processed and completed requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the number of processed requests (in purple) and completed requests (in green), by minute.
* You can hover over the chart to view points in time where the maximum number of requests was highest for that minute.

   ![Distinct Users graph](assets/requests-graph.png)

#### Queueing graph

The Queueing graph shows the average queue wait time (in seconds) for reporting requests for the selected report suite over the last 2 hours. 

* The x-axis shows a 2-hour time frame.
* The y-axis shows the average wait time (in seconds).
* You can hover over the chart to view points in time where the maximum average wait time was highest for that minute.

   ![Distinct Users graph](assets/queueing-graph.png)

-->

### Visa register {#view-table}

Du kan välja att visa data genom att välja någon av följande flikar högst upp i datatabellen: [!UICONTROL **Begäran**], [!UICONTROL **Användare**], [!UICONTROL **Projekt**], eller [!UICONTROL **Program**].

>[!TIP]
>
>Du kan välja [!UICONTROL **Göm diagram**] om du bara vill visa tabellen.

![tabellflikar](assets/indiv-report-ste-table-tabs.png)

#### Visa data på begäran

När du väljer [!UICONTROL **Begäran**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **ID för begäran**] | Kan användas i felsökningssyfte. |
| [!UICONTROL **Körning av tid**] | Hur länge begäran har körts. |
| [!UICONTROL **Starttid**] | När begäran började bearbetas (baserat på administratörens lokala tid). |
| [!UICONTROL **Väntetid**] | Hur länge begäran har väntat innan den bearbetas. I allmänhet vid &quot;0&quot; när det finns tillräckligt med kapacitet. |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. Om värdet för den här kolumnen är [!UICONTROL **Okänd**] innebär det att användaren är på ett inloggningsföretag där du inte har administratörsbehörighet. |
| [!UICONTROL **Projekt**] | Sparade projektnamn för arbetsytan, API-rapport-ID:n osv. (Metadata kan variera mellan olika program.) |
| [!UICONTROL **Status**] | Statusindikatorer: <ul><li>**Körs**: Begäran bearbetas för närvarande.</li><li>**Väntande**: Begäran väntar på att bearbetas.</li></ul> |
| [!UICONTROL **Komplex**] | Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran. Möjliga värden är: <ul><li>[!UICONTROL **Låg**]</li><li>[!UICONTROL **Medel**]</li><li>[!UICONTROL **Hög**]</li></ul>Värdet påverkas av värdena i följande kolumner:<ul><li>[!UICONTROL **Månadsgränser**]</li><li>[!UICONTROL **Kolumner**]</li><li>[!UICONTROL **Segment**]</li></ul> |
| [!UICONTROL **Månadsgränser**] | Antalet månader som ingår i en begäran. Detta ökar komplexiteten i begäran. |
| [!UICONTROL **Kolumner**] | Antalet mått och uppdelningar i begäran. Detta ökar komplexiteten i begäran. |
| [!UICONTROL **Segment**] | Antalet segment som används i begäran. Detta ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data per användare

När du väljer [!UICONTROL **Användare**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. Om värdet för den här kolumnen är [!UICONTROL **Okänd**] innebär det att användaren är på ett inloggningsföretag där du inte har administratörsbehörighet. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som initierats av användaren. |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med användaren. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som initierats av användaren. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Detta ökar den genomsnittliga komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Detta ökar den genomsnittliga komplexiteten. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Detta ökar den genomsnittliga komplexiteten. |

{style="table-layout:auto"}

#### Visa data efter projekt

När du väljer [!UICONTROL **Projekt**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Projekt**] | Det projekt där frågorna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med projektet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med projektet. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten hos begäranden som ingår i projektet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Detta ökar den genomsnittliga komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Detta ökar den genomsnittliga komplexiteten. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Detta ökar den genomsnittliga komplexiteten. |

{style="table-layout:auto"}

#### Visa data efter program

När du väljer [!UICONTROL **Program**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Program**] | Det program där frågorna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med programmet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med programmet. <!--???--> |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med programmet. <!--???--> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som är associerade med programmet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:<ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Detta ökar den genomsnittliga komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Detta ökar den genomsnittliga komplexiteten. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Detta ökar den genomsnittliga komplexiteten. |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this report suite. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

-->


