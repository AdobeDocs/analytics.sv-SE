---
title: Spåra på olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Spåra på olika implementeringstyper

En Adobe Analytics-implementations kärnarkitektur är enhetlig för alla implementeringstyper. Processen innefattar att definiera variabler och kompilera dem till en bildbegäran som skickas till Adobe datainsamlingsservrar. Detta innebär att du kan växla mellan AppMeasurement, Web SDK och deras respektive tillägg i Adobe Experience Platform Data Collection på olika sidor på samma webbplats.

Adobe rekommenderar att enhetlighet bibehålls i implementeringen av en webbplats genom att använda samma implementeringstyp på alla sidor. Men om delar av webbplatsen har olika krav kan du använda den här sidan för att se till att besökarna spåras konsekvent mellan sidorna.

Om du använder mer än en typ av implementering (t.ex. AppMeasurement och hårdkodade bildbegäranden) måste du se till att följande variabler är korrekt inställda och matchar varandra:

| Variabel | AppMeasurement | Analystillägg | Webb-SDK | Web SDK-tillägg | Hårdkodad bildbegäran |
| --- | --- | --- | --- | --- | --- |
| Rapportsvit-ID | Strängargument i [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] under [!UICONTROL Library management] sektion när [Konfigurera tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Lägg till Adobe Analytics som en tjänst när [Konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Lägg till Adobe Analytics som en tjänst när [Konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Del av URL `pathname` (efter `/b/ss/`) |
| Spårningsserver | The [`trackingServer`](../vars/config-vars/trackingserver.md) och [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variabler | [!UICONTROL Tracking Server] och [!UICONTROL SSL Tracking Server] under [!UICONTROL General] sektion när [Konfigurera tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | The `edgeDomain` egenskap när [Konfigurera Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) | The [!UICONTROL Edge Domain] när [Konfigurera tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | The `hostname` URL för bildbegäran |
| Experience Cloud ID-tjänst | Implementering [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html) | Använd [Tjänsttillägg för Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Använd [Tjänsttillägg för Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Använd [Tjänsttillägg för Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Gör en [separat anrop till ID-tjänstservrarna](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) för att erhålla önskat ID |

{style="table-layout:auto"}

Om någon av dessa variabler inte är konsekvent för varje implementeringstyp ser Adobe dem som separata besökare. Om besökare inte spåras sömlöst över olika implementeringstyper på din webbplats är den vanligaste orsaken att ID-tjänsten är felaktigt konfigurerad. Se [Implementeringsmetoder](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) i användarhandboken för ID-tjänsten om du vill ha mer information.
