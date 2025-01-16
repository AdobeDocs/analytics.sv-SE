---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren

Med [!UICONTROL Reporting Activity Manager] kan administratörer snabbt diagnostisera och åtgärda problem med rapporttapacitet under perioder med hög rapporteringsnivå.

Mer information om Reporting Activity Manager, inklusive viktiga fördelar och behörighetskrav, finns i [Översikt över Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Visa rapporteringsaktivitet för alla rapportsviter {#view-all-report-suites}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_reportingactivitymanager_connections"
>title="Anslutningar"
>abstract="Den här tabellen visar de anslutningar som du har behörighet att hantera rapporteringsaktivitet för. Information om varje anslutning finns i varje kolumn i tabellen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_reportingactivitymanager_connections"
>title="Anslutningar"
>abstract="Den här tabellen visar de anslutningar som du har behörighet att hantera rapporteringsaktivitet för. Information om varje anslutning finns i varje kolumn i tabellen."

<!-- markdownlint-enable MD034 -->

1. Gå till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]** i Adobe Analytics.

   En lista över dina aktiverade basrapportsviter visas.

   ![rapportkö](assets/reporting-activity1.png)

1. (Valfritt) Du kan söka efter eller filtrera listan med rapportsviter:

   * Använd sökfältet för att söka efter en specifik rapportsserie. Börja skriva rapportsvitens namn eller ID och listan över rapportsviter uppdateras medan du skriver.

   * Välj ikonen [!UICONTROL **Filter**] ![Filter ](assets/filter-icon.png) för att expandera listan med filteralternativ. Du kan filtrera efter [!UICONTROL **Favoriter**] eller [!UICONTROL **Status**].

     Om du vill markera en rapportserie som favorit väljer du stjärnikonen till vänster om rapportsvitens namn.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Visa användningsinformation om varje rapportserie. De data som visas i tabellen representerar rapportaktiviteten för rapportsviten när sidan senast lästes in.

   Följande kolumner är tillgängliga:

   | Gränssnittselement | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Report Suite]** | Basrapportsviten vars rapporteringsaktivitet du övervakar. |
   | **[!UICONTROL Virtual report suites]** | Visar alla virtuella rapportsviter som matas in i denna basrapportsserie. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla begäranden som kommer från de virtuella rapportsviterna kombineras i basrapportsviten. |
   | **[!UICONTROL Capacity utilization]** | Procentandelen av rapportsvitens rapporteringskapacitet som används i realtid. <p>**Obs!** En användningskapacitet som är 100 % behöver inte innebära att du omedelbart bör avbryta rapporteringsbegäranden. 100 % användningskapacitet kan vara hälsosam om den genomsnittliga väntetiden är rimlig. Å andra sidan kan 100 % av användningskapaciteten tyda på ett problem om antalet begäranden som står i kö också ökar.</p> |
   | **[!UICONTROL Queued requests]** | Antalet begäranden som väntar på att behandlas. <!-- ??? --> |
   | **[!UICONTROL Queue wait time]** | Genomsnittlig väntetid innan begäranden börjar bearbetas. <!-- ???? --> |
   | **[!UICONTROL Status]** | Möjliga statusvärden är: <ul><li>[!UICONTROL **Aktiv**] (blå): Rapporter har körts på rapportsviten under de senaste två timmarna. De data som visas i tabellen representerar rapportkapaciteten för rapportsviten när sidan senast lästes in.</li><li>[!UICONTROL **Inaktiv**] (grå): Inga rapporter har körts på rapportsviten under de senaste två timmarna, så inga data visas för rapportsviten.</li></ul> |

   {style="table-layout:auto"}

## Visa rapporteringsaktivitet för en enskild rapportserie

1. I Adobe Analytics väljer du [!UICONTROL **Admin**] > [!UICONTROL **Rapportera aktivitetshanterare**].

1. Markera den länkade titeln för den rapportsserie som du vill visa information om.

   Rapporteringsaktivitetsdata visas för den rapportserie som du har valt.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. (Valfritt) När en anslutning först läses in i Rapporteringsaktivitetshanteraren representerar de data som visas aktuella användningsmått. Om du vill se uppdaterade mätvärden efter den första inläsningen väljer du knappen [!UICONTROL **Uppdatera**] för att uppdatera sidan manuellt.

1. Använd tillgängliga diagram och tabeller för att förstå rapporteringsaktiviteten i rapportsviten.

   * [Visa diagram](#view-graphs)

   * [Visa register](#view-table)

### Visa diagram

Följande diagram är tillgängliga för att hjälpa dig att bättre förstå vad som händer i rapportsviten.

Om diagrammen inte visas markerar du knappen [!UICONTROL **Visa diagram**] .

#### Användningsdiagram {#utilization}

I användningsdiagrammet visas rapporteringsanvändning för den valda rapportsviten under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där procentandelen av användningskapaciteten var högst för den minuten.

* **X-axel**: Rapporterar användningskapacitet under de senaste två timmarna.
* **Y-axel**: Rapporterar användningskapacitet i procent per minut.

  ![utnyttjandediagram](assets/utilization-graph.png)

#### Diagram över distinkta användare

Diagrammet Distinkta användare visar rapporteringsaktiviteten för den valda rapportsviten under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där det högsta antalet användare var under den minuten.

* **X-axel**: Rapporteringsaktiviteten under den senaste 2-timmars tidsramen.
* **Y-axel**: Antalet användare som har gjort rapportförfrågningar, per minut.

  ![Diagram över distinkta användare](assets/distinct-users-graph.png)

#### Begärandiagram

I diagrammet Begäranden visas antalet bearbetade och köade begäranden för den valda rapportsviten under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där det högsta antalet förfrågningar för den minuten var högst.

* **X-axel**: Antalet bearbetade och slutförda begäranden under den senaste 2-timmars tidsramen.
* **Y-axel**: Antalet bearbetade begäranden (i grönt) och begäranden i kö (i lila), per minut.

  ![Diagram över distinkta användare](assets/requests-graph.png)

#### Köar diagram

I ködiagrammet visas den genomsnittliga väntetiden i kön (i sekunder) för rapportbegäranden för den valda rapportsviten under de senaste två timmarna.

Håll pekaren över diagrammet om du vill visa tidpunkter där den maximala genomsnittliga väntetiden var högst för den minuten.

* **X-axel**: Den genomsnittliga köväntetiden för rapportering av begäranden under den senaste 2-timmars tidsramen.
* **Y-axel**: Genomsnittlig väntetid (i sekunder).

  ![Diagram över distinkta användare](assets/queueing-graph.png)

### Visa register {#view-table}

Tänk på följande när du visar tabellen:

* Du kan välja att visa data genom att välja någon av följande flikar högst upp i datatabellen: [!UICONTROL **Request**], [!UICONTROL **User**], [!UICONTROL **Project**] eller [!UICONTROL **Application**].

* Du kan söka efter eller filtrera listan över anslutningar:

   * Använd sökfältet för att söka efter en viss anslutning. Börja skriva anslutningsnamnet eller ID:t och listan över anslutningar som uppdateras medan du skriver.

   * Välj ikonen [!UICONTROL **Filter**] ![Filter ](assets/filter-icon.png) för att expandera listan med filteralternativ. Du kan filtrera efter [!UICONTROL **Status**], [!UICONTROL **Komplexitet**], [!UICONTROL **Program**], [!UICONTROL **Användare**] eller [!UICONTROL **Projekt**].

   * Du kan välja [!UICONTROL **Dölj diagram**] om du bara vill visa tabellen.

![tabellflikar](assets/report-activity-tabs.png)

#### Visa data på begäran

När du väljer fliken [!UICONTROL **Begäran**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **ID för förfrågan**] | Ett unikt ID som kan användas för felsökning. Om du vill kopiera ID:t markerar du begäran och väljer sedan alternativet [!UICONTROL **Kopiera ID:n för begäran**]. |
| [!UICONTROL **Tid för körning**] | Hur länge begäran har körts. |
| [!UICONTROL **Starttid**] | När begäran började bearbetas (baserat på administratörens lokala tid). |
| [!UICONTROL **Väntetid**] | Hur länge begäran har väntat innan den bearbetas. Detta värde är vanligtvis&quot;0&quot; när det finns tillräckligt med kapacitet. |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Workspace reguljära projekt</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Aviseringar</li><li>Dela med alla länkar</li><li>Alla andra program som frågar efter analysrapportmotorn</li></ul> |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. <p>**Obs!** Om värdet för den här kolumnen är [!UICONTROL **Okänt**] innebär det att användaren befinner sig i ett inloggningsföretag där du inte har administratörsbehörighet.</p> |
| [!UICONTROL **Projekt**] | Sparade projektnamn, API-rapport-ID:n för Workspace osv. (Metadata kan variera mellan olika program.) |
| [!UICONTROL **Status**] | Statusindikatorer: <ul><li>**Körs**: Begäran bearbetas.</li><li>**Väntande**: Begäran väntar på att bearbetas.</li></ul> |
| [!UICONTROL **Komplexitet**] | Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran. <p>Möjliga värden är:</p> <ul><li>[!UICONTROL **Låg**]</li><li>[!UICONTROL **Medium**]</li><li>[!UICONTROL **Hög**]</li></ul>Värdet påverkas av värdena i följande kolumner:<ul><li>[!UICONTROL **Månadsgränser**]</li><li>[!UICONTROL **Kolumner**]</li><li>[!UICONTROL **Segment**]</li></ul> |
| [!UICONTROL **Månadsgränser**] | Antalet månader som ingår i en begäran. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Kolumner**] | Antalet mått och uppdelningar i begäran. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Segment**] | Antalet segment som används i begäran. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data per användare

När du väljer fliken [!UICONTROL **Användare**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Användare**] | Användaren som initierade begäran. Om värdet för den här kolumnen är [!UICONTROL **Okänd**] innebär det att användaren befinner sig i ett inloggningsföretag där du inte har administratörsbehörighet. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som initierats av användaren. |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med användaren. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Workspace reguljära projekt</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Aviseringar</li><li>Dela med alla länkar</li><li>Alla andra program som frågar efter analysrapportmotorn</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som initierats av användaren. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data efter projekt

När du väljer fliken [!UICONTROL **Projekt**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Projekt**] | Det projekt där förfrågningarna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med projektet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med projektet. <!-- ??? --> |
| [!UICONTROL **Program**] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Workspace reguljära projekt</li><li>Report Builder</li><li>Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Aviseringar</li><li>Dela med alla länkar</li><li>Alla andra program som frågar efter analysrapportmotorn</li></ul> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten hos begäranden som ingår i projektet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p><ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

#### Visa data efter program

När du väljer fliken [!UICONTROL **Program**] är följande kolumner tillgängliga i tabellen:

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL **Program**] | Programmet där förfrågningarna initierades. |
| [!UICONTROL **Antal begäranden**] | Antalet begäranden som är associerade med programmet. |
| [!UICONTROL **Antal användare**] | Antalet användare som är associerade med programmet. <!--???--> |
| [!UICONTROL **Antal projekt**] | Antalet projekt som är associerade med programmet. <!--???--> |
| [!UICONTROL **Genomsnittlig komplexitet**] | Den genomsnittliga komplexiteten för begäranden som är associerade med programmet. <p>Alla begäranden kräver inte samma tid för att behandlas. Komplexa begäranden kan ge en allmän uppfattning om hur lång tid som krävs för att behandla begäran.</p><p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:</p>Värdet i den här kolumnen baseras på en poäng som bestäms av värdena i följande kolumner:<ul><li>[!UICONTROL **Genomsnittliga månadsgränser**]</li><li>[!UICONTROL **Genomsnittliga kolumner**]</li><li>[!UICONTROL **Genomsnittliga segment**]</li></ul> |
| [!UICONTROL **Genomsnittliga månadsgränser**] | Genomsnittligt antal månader som ingår i begäranden. Fler månadsgränser gör begäran ännu mer komplex. |
| [!UICONTROL **Genomsnittliga kolumner**] | Genomsnittligt antal mått och uppdelningar i inkluderade begäranden. Fler kolumner ökar komplexiteten i begäran. |
| [!UICONTROL **Genomsnittliga segment**] | Genomsnittligt antal segment som tillämpas på de inkluderade förfrågningarna. Fler segment ökar komplexiteten i begäran. |

{style="table-layout:auto"}

<!--

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
|  |  |

{style="table-layout:auto"}

-->