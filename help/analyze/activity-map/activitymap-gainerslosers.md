---
description: Med övertäckningar kan du konfigurera datavisualisering på flera sätt så att du enkelt kan se och förstå hur populära länkarna på en sida är.
title: Anpassningsbara överlagringar
feature: Activity Map
role: User, Admin
exl-id: 1e83d470-36e4-47bb-a262-ac12472b21c3
source-git-commit: ab6d3267bd6b503fe96ceea2b870c2e7cdf5d9f4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Anpassningsbara överlagringar

Med övertäckningar kan du konfigurera datavisualisering på flera sätt så att du enkelt kan se och förstå hur populära länkarna på en sida är.

Med övertäckningar kan du visualisera klickdata direkt på sidan. Det är det som skiljer ett visuellt analysverktyg som Activity Map från de flesta tabellverktyg och grafiska verktyg som Rapporter och analyser.

Activity Map har tre typer av övertäckningar:

* Övertoningsövertäckning (Heatmap)
* Bubbelövertäckning
* Övertäckning för matare och förlorare

Du kan också konfigurera [överläggsåtergivning för dynamiskt innehåll](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Öppna [Panelen Överläggsinställningar](/help/analyze/activity-map/activitymap-overlay-settings.md) och redigera tillgängliga alternativ.

När du hovrar över en övertäckning visas dess [information](/help/analyze/activity-map/activitymap-overlay-details.md).

## Övertoningsövertäckning (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

I övertoningsövertäckningen baseras färgintensiteten på länkens popularitet. Denna intensitet kan normaliseras för de 30 högsta rankningarna, eller en funktion för det absoluta måttvärdet.

Dessa mätvärden läggs ovanpå sidans länkar som en slags&quot;värmekarta&quot; för att besvara viktiga frågor, inklusive följande:

* Vad är värdet för en enskild sida?
* Vad är värdet för ett enskilt element på en sida?
* Vilken är den mest värdefulla&quot;digitala egendomen&quot; på en sida?

![](assets/gradient.png)

## Bubbelövertäckning {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

Bubbelövertäckningen visar övertäckningsinnehållet (mått, procent eller rankning) i en liten pratbubbla.

Bubbelövertäckningar visas när du markerar den här övertäckningen i verktygsfältet Övertäckningstyp. . Bubbelövertäckningar visas för alla länkar som matchar markeringen i [Inställningar för Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) (övre 30, övre 50, alla...). Övertoningsövertäckningar visas om det här alternativet inte är markerat.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Bubbelövertäckningar för undermenyer visas bara när du visar undermenyn:
>
>![](assets/bubbles_submenu.png)>

## Övertäckningar för matare och förlorare {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** är bara tillgängliga i Live-läge. De rapporterar förändringar i länkaktiviteten i realtid genom att jämföra mätvärden från den aktuella perioden med mätvärden från den senaste perioden. De ger dig ett visuellt övertygande sätt att se trender i realtid.

Denna realtidsövertäckning rangordnar klick baserat på förändringar i måttvärdet mellan föregående och aktuella perioder.

![](assets/gainers_losers.png)
