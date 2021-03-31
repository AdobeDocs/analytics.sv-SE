---
description: Med övertäckningar kan du konfigurera datavisualisering på flera sätt så att du enkelt kan se och förstå hur populära länkarna på en sida är.
title: Anpassningsbara överlagringar
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
feature: Activity Map
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---


# Anpassningsbara överlagringar

Med övertäckningar kan du konfigurera datavisualisering på flera sätt så att du enkelt kan se och förstå hur populära länkarna på en sida är.

Med övertäckningar kan du visualisera klickdata direkt på sidan. Det är det som skiljer ett visuellt analysverktyg som Activity Map från de flesta tabellverktyg och grafiska verktyg som Rapporter och analyser.

Activity Map har tre typer av övertäckningar:

* Övertoningsövertäckning (Heatmap)
* Bubbelövertäckning
* Övertäckning för matare och förlorare

Du kan också konfigurera [övertäckningsåtergivning för dynamiskt innehåll](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Om du vill ändra övertäckningarna öppnar du panelen [Övertäckningsinställningar](/help/analyze/activity-map/activitymap-overlay-settings.md) och redigerar de tillgängliga alternativen.

Om du hovrar över en övertäckning visas dess [information](/help/analyze/activity-map/activitymap-overlay-details.md).

## Övertoningsövertäckning (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

I övertoningsövertäckningen baseras färgintensiteten på länkens popularitet. Denna intensitet kan normaliseras för de 30 högsta rankningarna, eller en funktion för det absoluta måttvärdet.

Dessa mätvärden läggs ovanpå sidans länkar som en slags&quot;värmekarta&quot; för att besvara viktiga frågor, inklusive följande:

* Vad är värdet för en enskild sida?
* Vad är värdet för ett enskilt element på en sida?
* Vilken är den mest värdefulla&quot;digitala egendomen&quot; på en sida?

![](assets/gradient.png)

## Bubbelövertäckning {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

Bubbelövertäckningen visar övertäckningsinnehållet (mått, procent eller rankning) i en liten pratbubbla.

Bubbelövertäckningar visas när du markerar den här övertäckningen i verktygsfältet Övertäckningstyp. . Bubbelövertäckningar visas för alla länkar som matchar markeringen i [Activity Map Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all..). Övertoningsövertäckningar visas om det här alternativet inte är markerat.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Bubbelövertäckningar för undermenyer visas bara när du visar undermenyn:
>
>![](assets/bubbles_submenu.png)>

## Tona och tappa bort övertäckningar {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** är bara tillgängliga i Live-läge. De rapporterar förändringar i länkaktiviteten i realtid genom att jämföra mätvärden från den aktuella perioden med mätvärden från den senaste perioden. De ger dig ett visuellt övertygande sätt att se trender i realtid.

Denna realtidsövertäckning rangordnar klick baserat på förändringar i måttvärdet mellan föregående och aktuella perioder.

![](assets/gainers_losers.png)

