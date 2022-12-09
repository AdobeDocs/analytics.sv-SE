---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 2%

---

# Rapporteringsaktivitetshanteraren

>[!NOTE]
>
>Den här funktionen är för närvarande under betatestning.

The [!UICONTROL Reporting Activity Manager] gör att du kan se rapporteringskapaciteten för varje rapportserie i din organisation. Som administratör får ni detaljerad insyn i rapporteringen av förbrukning och hjälper er att enkelt diagnostisera och åtgärda kapacitetsproblem under högkvalitativa rapporteringstider.

När organisationen når upp till sin rapporteringskapacitet och upplever en försämring av rapportens prestanda, kan ni nu själva diagnostisera rapporteringsproblem utan att behöva kontakta Adobe kundtjänst eller tekniker. Du kan enkelt hantera rapporteringsköer i ett enda gränssnitt och omedelbart agera &#x200B; &#x200B; för att förbättra användarnas upplevelse. Det här verktyget:

* Informerar dig i realtid om din nuvarande rapportkapacitet i alla rapportsviter.
* Innehåller detaljerad rapportfrågeinformation om aktuella rapporteringsbegäranden, oavsett om de står i kö eller pågår.
* Gör att du kan optimera rapporteringskön genom att prioritera vissa och avbryta andra rapporteringsbegäranden för att frigöra kapacitet. Med andra ord kan du fråga i realtid: Är den här rapporten nödvändig just nu eller kan jag avbeställa den till förmån för mer brådskande rapporter?

## Öppna Rapporteringsaktivitetshanteraren

I Adobe Analytics går administratörer till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Behörigheter

Du behöver behörigheten Produktadministratör för Analytics (i Adobe Admin Console) för att hantera rapporteringsaktivitet.

![behörighet](/help/admin/admin/assets/rep-mgr-permission.png)

## Visa rapportkön

När du öppnar [!UICONTROL Reporting Activity] På sidan Översikt över chefen visas en lista med dina aktiverade basrapportsviter.

![rapportkö](/help/admin/admin/assets/reporting-activity1.png)

| Gränssnittselement | Beskrivning |
| --- | --- |
| **[!UICONTROL Report Suite]** | Basrapportsviten vars rapporteringsaktivitet du övervakar. |
| **[!UICONTROL Virtual Report Suite]** | Visar alla virtuella rapportsviter som matas in i den här basrapportsviten. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla förfrågningar som kommer från de virtuella rapportsviterna kombineras och kommer ned till basrapportsviten.<p>Om du till exempel har 10 begäranden från 5 VRS är det 50 förfrågningar från rapportsviten på basnivå. På så sätt kan du snabbt nå ut till din kapacitet. |
| **[!UICONTROL Usage Capacity]** | Procentandel av rapportsvitens rapporteringskapacitet används i realtid. |
| **[!UICONTROL Status]** | Fyra möjliga statusindikatorer: <ul><li>**Röd -[!UICONTROL At Capacity]**: Rapportsviten är maximerad när det gäller rapporteringskapacitet. (100 %) </li><li>**Gul -[!UICONTROL Nearing capacity]**: Denna rapportserie riskerar att nå sin maximala kapacitet. (90-99 %)</li><li>**Grön -[!UICONTROL All good]**: Det finns gott om kapacitet för rapportering. (0 % - 89 %)</li><li>**Grå -[!UICONTROL Status pending/Not enabled]**: Rapportkapaciteten är inte tillgänglig.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Andra åtgärder för rapporteringsaktivitet

* Klicka **[!UICONTROL Refresh]** längst upp till höger för att uppdatera resultaten.
* Klicka på stjärnan till vänster om rapportsvitens namn för att favoriten i den här rapportsviten.
* Kontrollera **[!UICONTROL Favorites]** längst upp till vänster för att visa dina favoriter.
* Sök efter rapportsviter efter namn eller efter ID i sökfältet.
* Filtrera rapportsviter efter deras status.

## Visa rapporteringsaktivitet för enskilda rapportsviter

Klicka på titellänken för en rapportserie som du vill visa information om.

![rapportsvit](/help/admin/admin/assets/indiv-report-ste.png)

### Linjediagram

Raddiagrammet visar rapporteringsaktiviteten för den valda rapportsviten under de senaste två timmarna.

* X-axeln visar rapporteringskapaciteten under de senaste två timmarna.
* Y-axeln visar den genomsnittliga väntetiden för en fråga i sekunder.
* Du kan hovra över linjediagrammet för att visa punkter i tid och genomsnittlig väntetid för det tillfället.

   ![detalj](/help/admin/admin/assets/detail.png)

### Filter

Du kan filtrera tabellen efter program (se listan i tabellen nedan), efter användare och efter projekt.

![filter](/help/admin/admin/assets/filter.png)

### Sammanfattningsnummer

![filter](/help/admin/admin/assets/summary_numbers.png)

Följande information visas i sammanfattningsnumren:

| Sammanfattningsnummer | Beskrivning |
| --- | --- |
| [!UICONTROL Users] | Antalet användare som för närvarande skickar rapportbegäranden till den här rapportsviten. |
| [!UICONTROL Projects] | Arbetsyteprojekt, arbetsböcker från Report Builder osv. |
| [!UICONTROL Queries] | Antalet frågor som körs. |
| [!UICONTROL Average Wait Time] | Genomsnittlig väntetid för alla frågor som körs. |
| [!UICONTROL Usage Capacity] | Den aktuella användningskapaciteten för den här rapportsviten. |

{style=&quot;table-layout:auto&quot;}

### Tabell

I tabellen nedan finns information om rapportsviten.

| Kolumn | Beskrivning |
| --- | --- |
| [!UICONTROL Query ID] | Kan användas i felsökningssyfte. |
| [!UICONTROL Running Time] | Hur länge frågan har körts. |
| [!UICONTROL Wait Time] | Hur länge frågan har stått och väntat innan den bearbetades. I allmänhet vid &quot;0&quot; när det finns tillräckligt med kapacitet. |
| [!UICONTROL Start Time] | När frågan började bearbetas (administratörens lokala tid). |
| [!UICONTROL Application] | De program som stöds av [!UICONTROL Reporting Activity Manager] är: <ul><li>Analysis Workspace UI</li><li>Schemalagda projekt för arbetsyta</li><li>Report Builder</li><li>Användargränssnitt för Builder: Segment, beräknade värden, anteckningar, målgrupper osv.</li><li>API-anrop från 1.4 eller 2.0 API</li><li>Intelligenta aviseringar</li></ul> |
| [!UICONTROL User] | Användaren som initierade frågan. |
| [!UICONTROL Project] | Sparade projektnamn för arbetsytan, API-rapport-ID:n osv. (Metadata kan variera mellan olika program.) |
| [!UICONTROL Month Boundaries] | Hur många månatliga gränser en begäran överskrider. Detta ökar komplexiteten i begäran. |
| [!UICONTROL Columns] | Antalet mått och uppdelningar i Workspace för att mäta hur komplicerad begäran är. |
| [!UICONTROL Segments] | Hur många segment som används i den här begäran. Detta ökar komplexiteten i begäran. |
| [!UICONTROL Status] | Statusindikatorer: <ul><li>**Körs**: Begäran bearbetas.</li><li>**Väntande**: Begäran väntar på att bearbetas.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Avbryt rapporteringsbegäranden

Så här avbryter du en begäran

1. Markera rutan till vänster om en eller flera **[!UICONTROL Query ID]** i tabellen och klicka på **[!UICONTROL Cancel requests]** längst ned.

   Du kan även avbryta flera begäranden samtidigt genom att visa information via [!UICONTROL User], [!UICONTROL Project], eller [!UICONTROL Application]. Efterföljande begäranden för ett projekt, en användare eller ett program som inte var i kö eller som kördes när åtgärden avbröts kan fortfarande visas när aktiviteten uppdateras.

1. I **[!UICONTROL Cancel x query]** -fönstret som visas kan du ändra avbrottsmeddelandet om det behövs.
1. Klicka på **[!UICONTROL Continue]**.

   ![cancel-query](/help/admin/admin/assets/cancel-query.png)

Programanvändare i Workspace ser till exempel följande meddelande i sina projekt:

![cancel-user-notice](/help/admin/admin/assets/cancel-user-facing.png)

## Frågor och svar

| Fråga | Svar |
| --- | --- |
| Kan jag köpa ytterligare rapporteringskapacitet? | Den här funktionen kommer att vara tillgänglig inom den närmaste framtiden. |

{style=&quot;table-layout:auto&quot;}
