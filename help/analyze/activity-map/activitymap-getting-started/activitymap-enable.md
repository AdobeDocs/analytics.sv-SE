---
description: Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.
title: Aktivera Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---


# Aktivera och aktivera Activity Map

Beskriver de steg som Analytics Admin måste slutföra för att aktivera Activity Map-länksamling och användarhämtning.

## Steg 1. Aktivera Activity Map {#update_code}

Modulen Activity Map är en del av taggarna AppMeasurement.js, Adobe Experience Platform och Web SDK (alloy.js). Data från Activity Map kan inte samlas in om du inte uppdaterar till **Web SDK version 2.15.0** eller högre, eller **Adobe Analytics-taggtillägg v1.90** eller högre, eller **AppMeasurement version 1.6** eller senare.

+++Web SDK (tillägget Adobe Experience Platform-taggar)

1. I Adobe Experience Platform-taggar navigerar du till den egenskap som du implementerar Analytics för. Under [!UICONTROL Extensions] -> [!UICONTROL Adobe Experience Platform Web SDK], markera **[!UICONTROL Enable click data collection]** som markerats nedan.
1. Skapa biblioteket med ändringarna.
1. Publicera biblioteket i produktion.

![](assets/web_sdk.png)

**Validering**

Interagera samtal med fliken Developer Console Network:

1. Läs in utvecklingsstartskriptet på webbplatsen.
1. Om du klickar på Elements söker du efter &quot;/ee&quot; på fliken Nätverk

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Hämta och installera [Adobe Experience Platform debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Gå till [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Connect to Edge].

   ![](assets/validation2.jpg)

**Vanliga frågor**

* **Interaktionsanropet utlöses inte på fliken Nätverk.**
Med klickdatainsamlingen i ett samlarsamtal måste vi filtrera med antingen &quot;/ee&quot; eller &quot;collect?&quot;

* **Det finns ingen nyttolastvisning för samtalet.**
Samlingsanropet är utformat på ett sådant sätt att spårningen inte påverkar navigeringen till andra webbplatser, så att dokumentborttagningsfunktionen kan användas för samlarsamtal. Detta påverkar inte din datainsamling, men om du behöver validera på sidan lägger du till target = &quot;_blank&quot; till respektive element. Länken öppnas sedan på en ny flik.

* **Hur ignorerar jag samlingen av PII?**
Lägg till respektive villkor i&lt;&lt; före länk klicka på skicka återanrop>> och returnera false om du vill ignorera dessa värden. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html)

  Exempelkod:

  ![](assets/sample-code.png)

+++

+++Manuell implementering av Web SDK

Se [Spåra länkar](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) om du vill ha information om hur du implementerar länkspårning och hur du aktiverar Activity Map genom att hämta `region` för det klickade HTML-elementet.

>[!NOTE]
>
>Om du aktiverar länkspårning med Web SDK skickas länkhändelser när en kund navigerar från en sida till nästa. Detta skiljer sig från hur AppMeasurement fungerar och kan eventuellt resultera i extra fakturerbara träffar som skickas till Adobe.

+++

+++Analytics-tillägg (Adobe Experience Platform-taggar)

I Adobe Experience Platform-taggar navigerar du till den egenskap som du implementerar Analytics för. I [!UICONTROL Install Extension] dialogruta, välja **[!UICONTROL Use Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Ladda ned det senaste Javascript-biblioteket för AppMeasurement.
Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Implementera den genom att följa [dessa instruktioner](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html).

+++

## Steg 2. Aktivera Activity Map-rapporter {#enable}

Du måste aktivera Activity Map-rapporter på rapportsvitnivå.

1. Logga in på Adobe Analytics och navigera till  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .

1. Activity Map samlar in länkdata i Activity Map-rapporter. För att aktivera måste du först aktivera variablerna genom att klicka på **[!UICONTROL Enable Activity Map Reports]**.

   I det här steget läggs alla analysdimensioner till som du behöver för att samla in data.

   ![](assets/enable.png)

1. Efter ungefär en timme ska du kontrollera [Activity Map Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), som visar alla sidor där användarna klickade på en länk.

## Steg 3. Lägg till användare i [!UICONTROL Activity Map Access] produktprofil {#add_users}

1. Klicka på **[!UICONTROL Add Users to Group]**.

   Då kommer du till produktprofilsidan på sidan [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Om du inte har skapat en [!UICONTROL Activity Map Access] produktprofil, gör det nu. Behörighetsobjekten som krävs för profilen är [!UICONTROL Analytics Tools] > [!UICONTROL Activity Map] och [!UICONTROL Analytics Tools] > [!UICONTROL Segment Publishing].

1. Lägg till användare i den produktprofilen. Detta gör att dina användare kan hämta Activity Map från  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

