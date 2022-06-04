---
title: Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK
description: Använd SDK-tillägget för mobiler i Adobe Experience Platform Data Collection för att skicka data till Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK

Adobe Experience Platform Mobile SDK hjälper er att driva lösningar och tjänster från Adobe Experience Cloud i era mobilappar. Det finns för Android, iOS och olika plattformsoberoende utvecklingsramverk. Konfigurationen hanteras med användargränssnittet i Adobe Experience Platform Data Collection.

Så här skickar du data till Adobe Experience Edge med Mobile SDK:

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection).
2. Välj önskad egenskap i listan, eller [konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Gå till fliken Tillägg och installera [Identitet för Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) tillägg.
4. Installera [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Konfigurera ett datastream](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), lägger till Adobe Analytics som en tjänst som pekar på önskat rapportpaket.
6. [Installera SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) i mobilappen.

>[!IMPORTANT]
>
>Ett Adobe Analytics-tillägg finns också i användargränssnittet för datainsamling. Om du installerar det här tillägget kan du inte utnyttja XDM eller Edge Network.
