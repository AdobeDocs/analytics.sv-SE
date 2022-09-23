---
title: collectHighEntropyUserAgentHints
description: Använd variabeln collectHighEntropyUserAgentHints för att avgöra om Adobe ska begära höga entropittips från Chromium-webbläsare (t.ex. Google Chrome och Microsoft Edge).
source-git-commit: 9c386dd26e31b8b2dc2b4a52ae502f9505ec467d
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---


# collectHighEntropyUserAgentHints

Högupplösta klienttips används av Adobe Analytics för att förbättra enhets- och webbläsaridentifieringen. Läs mer om kundtips i [denna översikt och vanliga frågor](/help/technotes/client-hints.md) och [Google blogg](https://web.dev/user-agent-client-hints/).

## Samla in höga entropytips med Web SDK

Högupplösta klienttips ingår i kontextkategorierna i Web SDK. Se [Konfigurera Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) för mer information.

## Samla in höga entropytips med Adobe Analytics Extension

**[!UICONTROL Collect high-entropy user-agent hints]** är en kryssruta under dragspelsfliken Allmänt när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) med inloggningsuppgifterna för ditt AdobeID.

1. Klicka på önskat [!UICONTROL tag property].

1. Gå till [!UICONTROL Extensions] tabbtangenten och sedan klicka [!UICONTROL Configure] under Adobe Analytics.

1. Expandera [!UICONTROL General] dragspelspanel, som visar [!UICONTROL Collect high entropy user-agent hints] kryssruta. Den är avmarkerad som standard.

## collectHighEntropyUserAgentHints in AppMeasurement

The `s.collectHighEntropyUserAgentHints` variabeln avgör om AppMeasurement begär höga entropytips från Chromium-webbläsare (t.ex. Google Chrome och Microsoft Edge). Dessa tips används av Adobe Analytics för att förbättra enhets- och webbläsaridentifieringen.

Om värdet är TRUE kommer alla höga entropytips att begäras från webbläsaren.

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`