---
description: Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och hämtning av användare.
title: Aktivera aktivitetskarta
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Aktivera aktivitetskarta{#enable-activity-map}

Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och hämtning av användare.

## Steg 1. Uppdatera din AppMeasurement-kod (JavaScript) till v1.6 (eller senare) {#section_5D1586289DF2489289B1B6C1C80C300D}

Aktivitetskartan är en del av filen AppMeasurement.js (som finns högst upp i filen). AppMeasurement-biblioteket läser in aktivitetskartmodulen när den instansieras.

Data för aktivitetskartan kan inte samlas in om du inte uppdaterar till den här versionen (eller senare) av AppMeasurement.

1. Hämta den senaste AppMeasurement-koden (AppMeasurement_Javascript-1.6.zip) genom att gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** och [implementera den](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Vi har inkluderat en del [exempelkod](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) för implementering som hjälper dig att visualisera de ändringar som har gjorts i koden genom att inkludera aktivitetskartan.

1. Validera implementeringen:

   1. När du klickar på ett klickbart element lagras data i en cookie med namnet s_sq.
   1. Data för aktivitetskartan visas i frågesträngen för spårningsanropet. Exempel:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Bryt ned den här rapporten **[!UICONTROL Activity Map Link by Region]** för att se länken/regionen för den sidan:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## Steg 2. Aktivera rapporter för aktivitetskarta {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Först måste du aktivera aktivitetskartrapporter på rapportsvitnivå.

1. Logga in på Adobe Analytics och gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites >[välj Report suite]> Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map samlar in länkdata i aktivitetskartrapporter. För att aktivera måste du först aktivera variablerna genom att klicka på **[!UICONTROL Enable Activity Map Reports]**.

   I det här steget läggs alla analysdimensioner till som du behöver för att samla in data.

1. Efter ungefär en timme kontrollerar du rapporten [](/help/analyze/activity-map/activitymap-reporting-analytics.md)Activity Map Page, som visar alla sidor där användarna klickade på en länk.

## Steg 3. Lägg till användare i åtkomstgruppen för aktivitetskartan {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Klicka på **[!UICONTROL Add Users to Group]**.

   Du kommer nu till grupphanteringssidan i Admin Console.

1. [Lägg till användare i den här gruppen](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) och **[!UICONTROL Save Group]**.

1. Detta gör att dina Admin-användare kan hämta aktivitetskartan från **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

> [!NOTE] Om du vill att användare som inte är administratörer ska hämta aktivitetskartan skapar du en ny användargrupp som ger behörighet till Tools och Legacy ClickMap Installation. Den här behörighetsnivån kombinerat med åtkomst till aktivitetskartan ger behörighet att hämta och använda verktyget.
