---
title: Spåra olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Spåra olika implementeringstyper

En Adobe Analytics-implementations kärnarkitektur är enhetlig för alla implementeringstyper. Processen innefattar att definiera variabler och kompilera dem till en bildbegäran som skickas till Adobe datainsamlingsservrar. Detta innebär att du kan växla mellan AppMeasurement, Web SDK och deras respektive tillägg i Adobe Experience Platform Data Collection på olika sidor på samma webbplats.

Adobe rekommenderar att enhetlighet bibehålls i implementeringen av en webbplats genom att använda samma implementeringstyp på alla sidor. Men om delar av webbplatsen har olika krav kan du använda den här sidan för att se till att besökarna spåras konsekvent mellan sidorna.

Om du använder mer än en typ av implementering (t.ex. AppMeasurement och hårdkodade bildbegäranden) måste du se till att följande variabler är korrekt inställda och matchar varandra:

| Variabel | AppMeasurement | Analystillägg | Webb-SDK | Web SDK-tillägg | Hårdkodad bildbegäran |
| --- | --- | --- | --- | --- | --- |
| Rapportsvit-ID | Strängargument i [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] under avsnittet [!UICONTROL Library management] när [Konfigurerar tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Del av URL:en `pathname` (efter `/b/ss/`) |
| Spårningsserver | Variablerna [`trackingServer`](../vars/config-vars/trackingserver.md) och [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Tracking Server] och [!UICONTROL SSL Tracking Server] under avsnittet [!UICONTROL General] när [tillägget konfigureras](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Egenskapen `edgeDomain` när [Web SDK konfigureras](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) | [!UICONTROL Edge Domain] när [Tillägget konfigureras](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | `hostname` för bildbegärans URL |
| Experience Cloud ID-tjänst | Implementera [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html) | Använd [Adobe Experience Cloud ID-tjänsttillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Använd [Adobe Experience Cloud ID-tjänsttillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Använd [Adobe Experience Cloud ID-tjänsttillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Gör ett [separat anrop till ID-tjänstservrarna](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) för att hämta önskat ID |

{style="table-layout:auto"}

Om någon av dessa variabler inte är konsekvent för varje implementeringstyp ser Adobe dem som separata besökare. Om besökare inte spåras sömlöst över olika implementeringstyper på din webbplats är den vanligaste orsaken att ID-tjänsten är felaktigt konfigurerad. Mer information finns i [Implementeringsmetoder](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) i användarhandboken för ID-tjänsten.
