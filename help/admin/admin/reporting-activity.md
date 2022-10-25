---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Rapporteringsaktivitetshanteraren
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 6ab2f39bdfc3a50c2b91f020c98b0e81da8b2b8e
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

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
| **[!UICONTROL Report Suite]** | Basrapportsviten |
| **[!UICONTROL Virtual Report Suite]** | Alla virtuella rapportsviter som matas in i den här basrapportsviten. Virtuella rapporteringsprogram gör det enklare att rapportera förfrågningar på grund av ytterligare nivåer av tillämpad filtrering och segmentering. Alla förfrågningar som kommer från de virtuella rapportsviterna kombineras och kommer ned till basrapportsviten.<p>Om du har 10 förfrågningar från 5 VRS:er är det 50 förfrågningar på basnivån för rapportsviten. På så sätt kan du snabbt nå ut till din kapacitet. |
| **[!UICONTROL Usage Capacity]** | Procentandel av rapportsvitens rapporteringskapacitet används i realtid. |
| **[!UICONTROL Status]** | Fyra möjliga statusindikatorer: <ul><li>**Röd - vid kapacitet**: Rapportsviten är maximerad när det gäller rapporteringskapacitet.</li><li>**Gul - Kapacitet för närhet**: Denna rapportserie riskerar att nå sin maximala kapacitet.</li><li>**Grön - tillgänglig**: Det finns gott om kapacitet för rapportering.</li><li>**Grå - ej tillgänglig**: Rapportsviten är inte konfigurerad för rapporteringskapacitet.</li></ul> |

Uppdatera sidan om du vill ändra resultatet.

## Filtrera rapportsviter

Du kan filtrera rapportsviterna efter