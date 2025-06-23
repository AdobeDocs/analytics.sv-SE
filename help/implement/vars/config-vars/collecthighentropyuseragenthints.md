---
title: collectHighEntropyUserAgentHints
description: Använd variabeln collectHighEntropyUserAgentHints för att ta reda på om Adobe kommer att begära hög entropi från webbläsare i Chromium (t.ex. Google Chrome och Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# collectHighEntropyUserAgentHints

Högupplösta klienttips används av Adobe Analytics för att förbättra enhets- och webbläsaridentifieringen. Det här alternativet är tillgängligt från och med version 2.23.0 av AppMeasurement.js. Läs mer om klienttips i [den här översikten och Frågor och svar](/help/technotes/client-hints.md) samt [Google blogg](https://web.dev/user-agent-client-hints/).

## Samla in multimediala tips med Web SDK

Högupplösta klienttips ingår i kontextkategorierna i Web SDK. Mer information finns i [Konfigurera Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=sv-SE).

## Samla in entropiska tips med Adobe Analytics Extension

**[!UICONTROL Collect high-entropy user-agent hints]** är en kryssruta under dragspelsfliken Allmänt när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad [!UICONTROL tag property].
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på [!UICONTROL Configure] under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL General], som visar kryssrutan [!UICONTROL Collect high entropy user-agent hints]. Den är avmarkerad som standard.

## collectHighEntropyUserAgentHints i AppMeasurement

Variabeln `s.collectHighEntropyUserAgentHints` avgör om AppMeasurement begär tips för hög entropi från Chromium-webbläsare (till exempel Google Chrome eller Microsoft Edge). Dessa tips används av Adobe Analytics för att förbättra enhets- och webbläsaridentifieringen.

Om värdet är `true` kommer alla höga entropittips att begäras från webbläsaren.

```js
s.collectHighEntropyUserAgentHints = true;
```
