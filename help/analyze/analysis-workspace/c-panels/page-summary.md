---
description: På sidsammanfattningspanelen visas sammanfattningsinformation för en sida som du väljer.
title: Panelen Sidsammanfattning
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Panelen Sidsammanfattning {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Sidsammanfattning"
>abstract="Granska snabbt några av de högnivåstatistik som finns och hur man går från en viss sida till och från en viss sida."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Panelen Sidsammanfattning"
>abstract="Granska snabbt några av de högnivåstatistik som finns och hur man går från en viss sida till och från en viss sida.<br/><br/>**Parametrar **<br/>**Lägg till ett siddimensionsobjekt**: Öppna komponentfältet, leta upp siddimensionen och expandera den genom att klicka på moroten för att visa dimensionsobjekten. Dra och släpp sedan den sida du vill veta mer om i verktyget. När du har dragit och släppt dimensionsobjektet fylls rapporten automatiskt i med nyckelinformation om sidan."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar panelen Sidsammanfattning i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Det finns ingen motsvarande panel i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

På den här panelen kan du enkelt utforska nyckelstatistik om specifika sidor.

## Öppna panelen

Du kan komma åt panelen inifrån [!UICONTROL Reports] eller i [!UICONTROL Workspace].

| Åtkomstpunkt | Beskrivning |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Panelen har redan släppts i ett projekt.</li><li>Den vänstra listen är komprimerad.</li><li>Endast siddimensionen stöds.</li><li>En standardinställning har redan tillämpats, i det här fallet den översta besökta sidan för dimensionen [!UICONTROL Page]. Du kan ändra den här inställningen.</li></ul> |
| Workspace | Skapa ett nytt projekt och välj panelikonen i den vänstra listen. Dra panelen [!UICONTROL Page summary] ovanför friformstabellen. Observera att fältet Sida [!UICONTROL Dimension Item] är tomt. Välj en dimensionsobjekt i listrutan. |

## Panelindata {#Input}

Du kan konfigurera panelen [!UICONTROL Page summary] med följande indatainställningar:

| Inställning | Beskrivning |
| --- | --- |
| Släppzon för segment (eller annan komponent) | Du kan dra och släppa segment eller andra komponenter för att ytterligare filtrera panelresultaten. |
| Siddimensionsobjekt | I listrutan väljer du det sidodimensionsobjekt vars nyckelstatistik du vill utforska. |

{style="table-layout:auto"}

Klicka på **[!UICONTROL Build]** för att skapa panelen.

## Panelutdata {#output}

Panelen [!UICONTROL Page summary] returnerar en mängd mätdata och visualiseringar som hjälper dig att förstå statistik om specifika sidor bättre.

| Mätning/visualisering | Beskrivning |
| --- | --- |
| [!UICONTROL Page views] - Aktuell månad hittills | Antal sidvisningar för den här sidan för den aktuella månaden. |
| [!UICONTROL Page views] - 4 veckor före | Antal sidvisningar för den här sidan under den senaste månaden. |
| [!UICONTROL Page views] - 52 veckor före | Antal sidvisningar för den här sidan det senaste året. |
| [!UICONTROL Trend] | Ett trendat sidvydiagram för den här månaden, 4 veckor före och 52 veckor före. |
| [!UICONTROL Percentage of all page views] | Ett sammanfattningsnummer för procentandelen av alla sidvyer som gick till den här sidan. |
| [!UICONTROL Time spent on page] | Ett vågrätt stapeldiagram med en lista över hur lång tid som har tillbringats på sidan. |
| [!UICONTROL Single page visits] | Ett sammanfattningsnummer med en lista över antalet sidvyer där det här var den enda sidan som besöktes. |
| [!UICONTROL Reloads] | Måttet [!UICONTROL Reloads] visar hur många gånger ett dimensionsobjekt fanns under en omläsning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning. |
| [!UICONTROL Entries] | Måttet [!UICONTROL Entries] visar hur många gånger ett angivet dimensionsobjekt hämtas som det första värdet i ett besök. |
| [!UICONTROL Exits] | Måttet [!UICONTROL Exits] visar hur många gånger ett angivet dimensionsobjekt har hämtats som det sista värdet i ett besök. |
| [!UICONTROL Flow] | Ett flödesdiagram med den valda sidan som fokalpunkt. Du kan fördjupa dig i data precis som i ett [flödesdiagram](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

![Panelen Sidsammanfattning](assets/page-sum1.png)

![Mätvärden och flöde](assets/page-sum2.png)
