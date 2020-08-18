---
description: Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.
title: Aktivera Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 6%

---


# Aktivera Activity Map{#enable-activity-map}

Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.

## Steg 1. Uppdatera din AppMeasurement-kod (JavaScript) till v1.6 (eller senare) {#section_5D1586289DF2489289B1B6C1C80C300D}

Modulen Activity Map är en del av filen AppMeasurement.js (som finns högst upp i filen). AppMeasurement-biblioteket läser in modulen Activity Map när den instansieras.

Data från Activity Map kan inte samlas in om du inte uppdaterar till den här versionen (eller senare) av AppMeasurement.

1. Hämta den senaste AppMeasurement-koden (AppMeasurement_Javascript-1.6.zip) genom att gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** och [implementera den](https://docs.adobe.com/content/help/en/analytics/implementation/js/overview.html).

   Vi har inkluderat en del [exempelkod](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) för implementering som hjälper dig att visualisera de ändringar som har gjorts i koden genom att inkludera modulen Activity Map.

1. Validera implementeringen:

   1. När du klickar på ett klickbart element lagras data i en cookie med namnet s_sq.
   1. Data från Activity Map kan visas i frågesträngen i spårningsanropet. Exempel:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Bryt ned den här rapporten **[!UICONTROL Activity Map Link by Region]** för att se länken/regionen för den sidan:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## Steg 2. Aktivera Activity Map-rapporter {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Först måste du aktivera Activity Map-rapporter på rapportsvitnivå.

1. Logga in på Adobe Analytics och gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportsvit > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map samlar in länkdata i Activity Map-rapporter. För att aktivera måste du först aktivera variablerna genom att klicka på **[!UICONTROL Enable Activity Map Reports]**.

   I det här steget läggs alla analysdimensioner till som du behöver för att samla in data.

1. Efter ungefär en timme kontrollerar du rapporten [för](/help/analyze/activity-map/activitymap-reporting-analytics.md)Activity Map-sidan, som visar alla sidor där användare klickade på en länk.

## Steg 3. Lägg till användare i åtkomstgruppen Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Klicka på **[!UICONTROL Add Users to Group]**.

   Du kommer nu till grupphanteringssidan i Admin Console.

1. [Lägg till användare i den här gruppen](https://docs.adobe.com/content/help/sv-SE/analytics/admin/user-product-management/user-groups/groups.html) och **[!UICONTROL Save Group]**.

1. Detta gör att dina Admin-användare kan hämta Activity Map från **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE]
>
>Om du vill att användare som inte är administratörer ska hämta Activity Map skapar du en ny användargrupp som ger behörighet till Tools och Legacy ClickMap Installation. Den här behörighetsnivån kombinerat med Activity Map Access ger behörighet att hämta och använda verktyget.
