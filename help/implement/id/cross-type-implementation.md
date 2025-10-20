---
title: Spåra olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Spåra olika implementeringstyper

En Adobe Analytics-implementations kärnarkitektur är enhetlig för alla implementeringstyper. Processen innefattar att definiera variabler och kompilera dem till en bildförfrågan som skickas till Adobe datainsamlingsservrar. Detta innebär att du kan växla mellan AppMeasurement, Web SDK och deras respektive tillägg i Adobe Experience Platform Data Collection på olika sidor på samma webbplats.

Adobe rekommenderar att man upprätthåller en konsekvent implementering av en webbplats genom att använda samma implementeringstyp på alla sidor. Men om delar av webbplatsen har olika krav kan du använda den här sidan för att se till att besökarna spåras konsekvent mellan sidorna.

Om du använder mer än en typ av implementering (t.ex. AppMeasurement och hårdkodade bildbegäranden) måste du se till att följande variabler är korrekt inställda och matchar varandra.

>[!NOTE]
>
>Alla implementeringstyper måste använda samma typ av besökaridentifiering (äldre analys-ID eller Visitor ID-tjänst). Adobe rekommenderar att du använder Visitor ID-tjänsten i alla implementeringar där det är möjligt.

| Variabel | AppMeasurement | Analystillägg | Web SDK (Alloy) | SDK-taggtillägg | Hårdkodad bildbegäran |
| --- | --- | --- | --- | --- | --- |
| Rapportsvit-ID | Strängargument i [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] under avsnittet [!UICONTROL Library management] när [Konfigurerar tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=sv-SE) | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE) | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE) | Del av URL:en `pathname` (efter `/b/ss/`) |
| Experience Cloud ID-tjänst | Implementera [`VisitorAPI.js`](appmeasurement.md) | Använd [Experience Cloud ID-tjänsttillägget](analytics-extension.md) | [Inbyggt](alloy.md) | [Inbyggt](web-sdk-extension.md) | Gör ett [separat anrop till ID-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=sv-SE) för att hämta önskat ID och inkludera `mid` i frågesträngen |
| Edge | Variabeln [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL SSL Tracking Server] under avsnittet [!UICONTROL General] när [Konfigurerar tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=sv-SE) | Egenskapen `edgeDomain` vid [Konfigurera Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=sv-SE) | Fältet [!UICONTROL Edge Domain] när [tillägget konfigureras](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=sv-SE) | `hostname` för bildbegärans URL |

Om någon av dessa variabler inte är konsekvent för varje implementeringstyp kan Adobe se dem som separata besökare. Om besökare inte spåras sömlöst över olika implementeringstyper på din webbplats är den vanligaste orsaken att ID-tjänsten är felaktigt konfigurerad. Se till att varje implementeringstyp har samma Experience Cloud-ID (`mid`) på hela webbplatsen.
