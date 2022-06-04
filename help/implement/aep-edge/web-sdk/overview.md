---
title: Implementera Adobe Analytics med Adobe Experience Platform Web SDK
description: Använd Web SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 4%

---


# Implementera Adobe Analytics med Adobe Experience Platform Web SDK

Du kan använda [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) för att skicka data till Adobe Analytics. Den här implementeringsmetoden fungerar genom att översätta [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) till ett format som används av Analytics.

## Inställningar

Så här ställer du in Analytics för att ta emot XDM-data:

1. Installera och [konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) den [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

1. Se till att de tillämpliga rapportsviterna mappas till de data du vill ha. XDM-data flödar automatiskt till rapportsviten från Adobe Experience Edge.
