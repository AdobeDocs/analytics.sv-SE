---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
mini-toc-levels: 3
source-git-commit: 7c66414129e262954e5521a28b878424099ac6ad
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 2%

---


# Rapporteringsaktivitetshanteraren

>[!NOTE]
>
>Den här funktionen är för närvarande under betatestning.

Med Rapporteringsaktivitetshanteraren kan du se rapporteringskapaciteten för varje rapportsvit i organisationen. Som administratör får ni detaljerad insyn i rapporteringen av förbrukning och hjälper er att enkelt diagnostisera och åtgärda kapacitetsproblem under högkvalitativa rapporteringstider.

När organisationen når upp till sin rapporteringskapacitet och upplever en försämring av rapportens prestanda, kan ni nu själva diagnostisera rapporteringsproblem utan att behöva kontakta Adobe kundtjänst eller tekniker. Du kan enkelt hantera rapporteringsköer i ett enda gränssnitt och omedelbart agera &#x200B; &#x200B; för att förbättra användarnas upplevelse. Det här verktyget:

* Informerar dig i realtid om din nuvarande rapportkapacitet i alla rapportsviter.
* Innehåller detaljerad rapportfrågeinformation om aktuella rapporteringsbegäranden, oavsett om de står i kö eller pågår.
* Gör att du kan optimera rapporteringskön genom att prioritera vissa och avbryta andra rapporteringsbegäranden för att frigöra kapacitet. Med andra ord kan du fråga i realtid: Är den här rapporten nödvändig just nu eller kan jag avbeställa den till förmån för mer brådskande rapporter?

## Öppna Rapporteringsaktivitetshanteraren

I Adobe Analytics går administratörer till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Behörigheter

Du behöver behörighet som systemadministratör för Analytics för att hantera rapporteringsaktivitet. Produktadministratörsåtkomst är inte tillräckligt.

## Visa rapportkön

När du öppnar översiktssidan för Reporting Activity Manager visas en lista över dina aktiverade basrapportsviter.

![rapportkö](assets/reporting-activity1.png)

| Gränssnittselement | Beskrivning |
| --- | --- |
| **[!UICONTROL Report Suite]** | Basrapportsviten vars rapporteringsaktivitet du övervakar. |
| **[!UICONTROL Virtual Report Suite]** | Visar alla virtuella rapportsviter som matas in i den här basrapportsviten. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla förfrågningar som kommer från de virtuella rapportsviterna kombineras och kommer ned till basrapportsviten.<p>Om du till exempel har 10 begäranden från 5 VRS är det 50 förfrågningar från rapportsviten på basnivå. På så sätt kan du snabbt nå ut till din kapacitet. |
| **[!UICONTROL Usage Capacity]** | Procentandel av rapportsvitens rapporteringskapacitet används i realtid. |
| **[!UICONTROL Status]** | Fyra möjliga statusindikatorer: <ul><li>**Röd -[!UICONTROL At Capacity]**: Rapportsviten är maximerad när det gäller rapporteringskapacitet. (95 % - 100 %) </li><li>**Gul -[!UICONTROL Nearing capacity]**: Denna rapportserie riskerar att nå sin maximala kapacitet. (90-94 %)</li><li>**Grön -[!UICONTROL All good]**: Det finns gott om kapacitet för rapportering. (0 % - 90 %)</li><li>**Grå -[!UICONTROL Status pending]**: ?</li></ul> |

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
| Projekt | Arbetsyteprojekt, arbetsböcker från Report Builder osv. |
| Frågor | Antalet frågor som körs. |
| Genomsnittlig väntetid | Genomsnittlig väntetid för alla frågor som körs. |
| Förbrukningskapacitet | Den aktuella användningskapaciteten för den här rapportsviten. |

{style=&quot;table-layout:auto&quot;}

### Tabell

I tabellen nedan finns information om rapportsviten.

| Kolumn | Beskrivning |
| --- | --- |
| Fråge-ID | Kan användas i felsökningssyfte. |
| Körningstid | Hur länge frågan har körts. |
| Väntetid | Hur länge frågan har stått och väntat innan den bearbetades. I allmänhet vid &quot;0&quot; när det finns tillräckligt med kapacitet. |
| Starttid | När frågan började bearbetas (administratörens lokala tid). |
| Program | Följande program stöds av Rapporteringsaktivitetshanteraren: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för Builder: Segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API (5 samtidiga begäranden)</li><li>Intelligenta aviseringar</li></ul> |
| Användare | Användaren som initierade frågan. |
| Projekt | Arbetsyteprojekt, arbetsböcker från Report Builder osv. |
| Månadsgränser | Hur många månatliga gränser en begäran överskrider. Detta ökar komplexiteten i begäran. |
| Kolumner | Antalet mått och uppdelningar i Workspace för att mäta hur komplicerad begäran är. |
| Segment | Hur många segment som används i den här begäran. Detta ökar komplexiteten i begäran. |
| Status | Fyra möjliga statusindikatorer: <ul><li>**Röd -[!UICONTROL At Capacity]**: Rapportsviten är maximerad när det gäller rapporteringskapacitet. (95 % och uppåt)</li><li>**Gul -[!UICONTROL Nearing capacity]**: Denna rapportserie riskerar att nå sin maximala kapacitet (90-95 %).</li><li>**Grön -[!UICONTROL All good]**: Det finns gott om kapacitet för rapportering.</li><li>**[!UICONTROL Status pending]**: Status är inte tillgänglig.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Avbryt rapporteringsbegäranden

Så här avbryter du en begäran

1. Markera rutan till vänster om en eller flera **[!UICONTROL Query ID]** i tabellen och klicka på **[!UICONTROL Cancel requests]** längst ned.
1. I **[!UICONTROL Cancel x query]** -fönstret som visas kan du ändra avbrottsmeddelandet om det behövs.
1. Klicka på **[!UICONTROL Continue]**.

   ![cancel-query](assets/cancel-query.png)

Programanvändare i Workspace ser till exempel följande meddelande i sina projekt:

![cancel-user-notice](assets/cancel-user-facing.png)


## Frågor och svar

| Fråga | Svar |
| --- | --- |
| Kan jag köpa ytterligare rapporteringskapacitet? | Den här funktionen kommer att vara tillgänglig inom den närmaste framtiden. |
| Andra frågor? |  |

{style=&quot;table-layout:auto&quot;}
