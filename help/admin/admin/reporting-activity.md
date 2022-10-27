---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 123a2131be1a3cb23246e2ba591be645c7025b26
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 1%

---


# Rapporteringsaktivitetshanteraren

>[!NOTE]
>
>Den här funktionen är för närvarande under betatestning.

Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje rapportsvit i organisationen. Som administratör får ni detaljerad insyn i rapporteringen av förbrukning och hjälper er att enkelt diagnostisera och åtgärda kapacitetsproblem under högkvalitativa rapporteringstider. När organisationen når upp till sin rapporteringskapacitet och upplever en försämring av rapportens prestanda, kan ni nu själva diagnostisera rapporteringsproblem utan att behöva kontakta Adobe kundtjänst eller tekniker. Du kan enkelt hantera rapporteringsköer i ett enda gränssnitt och omedelbart agera &#x200B; &#x200B; för att förbättra användarnas upplevelse. Det här verktyget:

* Informerar dig om din nuvarande rapporteringskapacitet i alla rapportsviter.
* Innehåller detaljerad rapportfrågeinformation om aktuella rapporteringsbegäranden, oavsett om de står i kö eller pågår.
* Gör att du kan optimera rapporteringskön genom att prioritera vissa och avbryta andra rapporteringsbegäranden för att frigöra kapacitet. Med andra ord kan du fråga i realtid: Är den här rapporten nödvändig just nu eller kan jag avbeställa den till förmån för mer brådskande rapporter?

## Öppna Rapporteringsaktivitetshanteraren

I Adobe Analytics går administratörer till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Visa rapportkön

När du öppnar översiktssidan för Reporting Activity Manager visas en lista över dina aktiverade basrapportsviter.

![rapportkö](assets/reporting-activity1.png)

| Gränssnittselement | Beskrivning |
| --- | --- |
| **[!UICONTROL Report Suite]** | Basrapportsviten vars rapporteringsaktivitet du övervakar. |
| **[!UICONTROL Virtual Report Suite]** | Visar alla virtuella rapportsviter som matas in i den här basrapportsviten. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla förfrågningar som kommer från de virtuella rapportsviterna kombineras och kommer ned till basrapportsviten.<p>Om du till exempel har 10 begäranden från 5 VRS är det 50 förfrågningar från rapportsviten på basnivå. På så sätt kan du snabbt nå ut till din kapacitet. |
| **[!UICONTROL Usage Capacity]** | Procentandel av rapportsvitens rapporteringskapacitet används i realtid. |
| **[!UICONTROL Status]** | Fyra möjliga statusindikatorer: <ul><li>**Röd -[!UICONTROL At Capacity]**: Rapportsviten är maximerad när det gäller rapporteringskapacitet.</li><li>**Gul -[!UICONTROL Nearing capacity]**: Denna rapportserie riskerar att nå sin maximala kapacitet.</li><li>**Grön -[!UICONTROL All good]**: Det finns gott om kapacitet för rapportering.</li><li>**[!UICONTROL Status pending]**: ?</li><li>**Grå - ej tillgänglig**: Rapportsviten är inte konfigurerad för rapporteringskapacitet.</li></ul> |

### Andra åtgärder för rapporteringsaktivitet

* Klicka **[!UICONTROL Refresh]** längst upp till höger för att uppdatera resultaten.
* Klicka på stjärnan till vänster om rapportsvitens namn för att favoriten i den här rapportsviten.
* Kontrollera **[!UICONTROL Favorites]** längst upp till vänster för att visa dina favoriter.
* Sök efter rapportsviter efter namn eller efter ID i sökfältet.
* Filtrera rapportsviter efter deras status.

## Visa rapporteringsaktivitet för enskilda rapportsviter

Klicka på titellänken för en rapportserie som du vill visa information om.

![rapportsvit](assets/indiv-report-ste.png)

### Linjediagram

Raddiagrammet visar rapporteringsaktiviteten för den valda rapportsviten under de senaste två timmarna.

* X-axeln visar rapporteringskapaciteten under de senaste två timmarna.
* Y-axeln visar den genomsnittliga väntetiden för en fråga i sekunder.
* Du kan hovra över linjediagrammet för att visa punkter i tid och genomsnittlig väntetid för det tillfället.

   ![detalj](assets/detail.png)

### Filter

Du kan filtrera tabellen efter program (se listan i tabellen nedan), efter användare och efter projekt.

![filter](assets/filter.png)

### Sammanfattningsnummer

![filter](assets/summary_numbers.png)

Följande information visas i sammanfattningsnumren:

| Sammanfattningsnummer | Beskrivning |
| --- | --- |
| Användare | Hur många användare som för närvarande skickar rapportbegäranden till den här rapportsviten. |
| Projekt |  |
| Frågor |  |
| Genomsnittlig väntetid |  |
| Förbrukningskapacitet | Den aktuella användningskapaciteten för den här rapportsviten. |

{style=&quot;table-layout:auto&quot;}

### Tabell

Tabellen nedan visar

| Kolumn | Beskrivning |
| --- | --- |
| Fråge-ID |  |
| Körningstid |  |
| Väntetid |  |
| Starttid |  |
| Program | Följande program stöds av Rapporteringsaktivitetshanteraren: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för Builder: Segment, beräknade värden, anteckningar, målgrupper osv.</li></ul> |
| Användare |  |
| Projekt |  |
| Månadsgränser |
| Kolumner |  |
| Segment |  |
| Status |  |

{style=&quot;table-layout:auto&quot;}


