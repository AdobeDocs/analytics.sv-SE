---
description: Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.
title: Aktivera Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: 87c2f559990674ee738e1ad57166cf192d58232c
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 3%

---

# Aktivera Activity Map{#enable-activity-map}

Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.

## Steg 1. Uppdatera implementeringskoden {#section_5D1586289DF2489289B1B6C1C80C300D}

Modulen Activity Map är en del av AppMeasurement.js och Web SDK (version 2.15.0 eller senare).
AppMeasurement-biblioteket eller Web SDK läser in modulen Activity Map när den instansieras.

>[!NOTE]
>
>Data från Activity Map kan inte samlas in om du inte uppdaterar till **AppMeasurement** **version 1.6** eller högre eller **Web SDK** **version 2.15.0** eller högre


1. Hämta det senaste Javascript-biblioteket beroende på om du använder AppMeasurement eller Web SDK.

   - **AppMeasurement** kod (AppMeasurement_Javascript-1.6.zip) genom att gå till  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]** och [implementera](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html).

      Vi har tagit med några [exempelkod](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) för att hjälpa dig att visualisera de ändringar som har gjorts i koden genom att inkludera modulen Activity Map.

   - **Web SDK** kod (alloy.js). Se [Installera SDK - alternativ 2: Installera den fördefinierade fristående versionen](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) för mer information. Se till att du använder version 2.15 eller senare.

      Se [Spåra länkar](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) om du vill ha information om hur du implementerar länkspårning och hur du aktiverar aktivitetsmappning genom att hämta `region` för det klickade elementet HTML.

      >[!NOTE]
      >
      >Om du aktiverar länkspårning med Web SDK skickas länkhändelser när en kund navigerar från en sida till nästa. Detta skiljer sig från hur AppMeasurement fungerar och kan eventuellt resultera i extra fakturerbara träffar som skickas till Adobe.


1. Validera implementeringen:

   1. När du klickar på ett klickbart element lagras data i en cookie med namnet s_sq.
   1. Data från Activity Map kan visas i frågesträngen i spårningsanropet. Exempel:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Bryt ned rapporten med **[!UICONTROL Activity Map Link by Region]** för att se länken/regionen för den sidan:  ![](assets/am_breakdown.png){width="400px"}

## Steg 2. Aktivera Activity Map-rapporter {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Först måste du aktivera Activity Map-rapporter på rapportsvitnivå.

1. Logga in på Adobe Analytics och navigera till  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map samlar in länkdata i Activity Map-rapporter. För att aktivera måste du först aktivera variablerna genom att klicka på **[!UICONTROL Enable Activity Map Reports]**.

   I det här steget läggs alla analysdimensioner till som du behöver för att samla in data.

1. Efter ungefär en timme ska du kontrollera [Activity Map Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), som visar alla sidor där användarna klickade på en länk.

## Steg 3. Lägg till användare i åtkomstgruppen Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Klicka på **[!UICONTROL Add Users to Group]**.

   Du kommer nu till grupphanteringssidan i Admin Console.

1. [Lägg till användare i den här gruppen](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html) och **[!UICONTROL Save Group]**.

1. På så sätt kan administratörsanvändarna hämta Activity Map från  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE]
>
>Om du vill att användare som inte är administratörer ska hämta Activity Map skapar du en ny användargrupp som ger behörighet till Tools och Legacy ClickMap Installation. Den här behörighetsnivån kombinerat med Activity Map Access ger behörighet att hämta och använda verktyget.
