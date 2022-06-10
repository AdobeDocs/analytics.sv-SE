---
description: På sidsammanfattningspanelen visas sammanfattningsinformation för en sida som du väljer.
title: Panelen Sidsammanfattning
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: bef175d9675134f4932407a0b9e4a3c67b1d27a5
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Panelen Sidsammanfattning

The [!UICONTROL Page summary] som startats som en rapport i Rapporter och analyser, under Rapporter > Engagemang > Sidanalys > Sidsammanfattning. Det är nu även en arbetsytepanel. På den här panelen kan du enkelt utforska nyckelstatistik om specifika sidor.

## Öppna panelen

Du kommer åt panelen inifrån [!UICONTROL Reports] eller inom [!UICONTROL Workspace].

| Åtkomstpunkt | Beskrivning |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Panelen har redan släppts i ett projekt.</li><li>Den vänstra listen är komprimerad.</li><li>Endast siddimensionen stöds.</li><li>En standardinställning har redan använts, i det här fallet den översta besökta sidan för[!UICONTROL Page] dimension. Du kan ändra den här inställningen.</li></ul> |
| Arbetsyta | Skapa ett nytt projekt och välj panelikonen i den vänstra listen. Dra [!UICONTROL Page summary] ovanför friformstabellen. Observera att sidan [!UICONTROL Dimension Item] fältet är tomt. Välj en dimensionsobjekt i listrutan. |

## Panelindata {#Input}

Du kan konfigurera [!UICONTROL Page summary] med dessa indatainställningar:

| Inställning | Beskrivning |
| --- | --- |
| Släppzon för segment (eller annan komponent) | Du kan dra och släppa segment eller andra komponenter för att ytterligare filtrera panelresultaten. |
| Siddimensionsobjekt | I listrutan väljer du det sidodimensionsobjekt vars nyckelstatistik du vill utforska. |

{style=&quot;table-layout:auto&quot;}

Klicka **[!UICONTROL Build]** för att skapa panelen.

## Panelutdata {#output}

The [!UICONTROL Page summary] panelen returnerar en mängd mätdata och visualiseringar som hjälper dig att förstå statistik om specifika sidor bättre.

| Mätning/visualisering | Beskrivning |
| --- | --- |
| [!UICONTROL Page views] - Aktuell månad hittills | Antal sidvisningar för den här sidan för den aktuella månaden. |
| [!UICONTROL Page views] - 4 veckor före | Antal sidvisningar för den här sidan under den senaste månaden. |
| [!UICONTROL Page views] - 52 veckor före | Antal sidvisningar för den här sidan det senaste året. |
| [!UICONTROL Trend] | Ett trendat sidvydiagram för den här månaden, 4 veckor före och 52 veckor före. |
| [!UICONTROL Percentage of all page views] | Ett sammanfattningsnummer för procentandelen av alla sidvyer som gick till den här sidan. |
| [!UICONTROL Time spent on page] | Ett vågrätt stapeldiagram med en lista över hur lång tid som har tillbringats på den här sidan. |
| [!UICONTROL Single page visits] | Ett sammanfattningsnummer med en lista över antalet sidvyer där det här var den enda sidan som besöktes. |
| [!UICONTROL Reloads] | The [!UICONTROL Reloads] mått visar antalet gånger en dimensionsobjekt fanns under en omladdning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning. |
| [!UICONTROL Entries] | The [!UICONTROL Entries] mått visar hur många gånger en viss dimensionspost hämtas som det första värdet i ett besök. |
| [!UICONTROL Exits] | The [!UICONTROL Exits] mått visar hur många gånger en given dimensionspost hämtas som det sista värdet i ett besök. |
| [!UICONTROL Flow] | Ett flödesdiagram med den valda sidan som fokalpunkt. Du kan fördjupa dig i data precis som i [Flödesdiagram](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style=&quot;table-layout:auto&quot;}

![Panelen Sidsammanfattning](assets/page-sum1.png)

![Mätvärden och flöde](assets/page-sum2.png)
