---
title: Spåra olika implementeringstyper
description: Använd olika implementeringstyper och spåra besökare smidigt mellan dem.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
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

| Variabel | SDK-taggtillägg | Web SDK (Alloy) | Analystillägg | AppMeasurement | Hårdkodad bildbegäran |
|---|---|---|---|---|---|
| Rapportsvit-ID | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) | Lägg till Adobe Analytics som en tjänst när [Konfigurerar ett datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) | [!UICONTROL Report suites] under avsnittet [!UICONTROL Library management] när [Konfigurerar tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | Strängargument i [`s_gi`](../vars/functions/s-gi.md) | Del av URL:en `pathname` (efter `/b/ss/`) |
| Experience Cloud ID-tjänst | [Inbyggt](web-sdk-extension.md) | [Inbyggt](alloy.md) | Använd [Experience Cloud ID-tjänsttillägget](analytics-extension.md) | Implementera [`VisitorAPI.js`](appmeasurement.md) | Gör ett [separat anrop till ID-tjänsten](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) för att hämta önskat ID och inkludera `mid` i frågesträngen |
| Edge | Fältet [!UICONTROL Edge Domain] när [tillägget konfigureras](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | Egenskapen `edgeDomain` vid [Konfigurera Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL SSL Tracking Server] under avsnittet [!UICONTROL General] när [Konfigurerar tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | Variabeln [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | `hostname` för bildbegärans URL |

Om någon av dessa variabler inte är konsekvent för varje implementeringstyp ser Adobe dem som separata besökare. Om besökare inte spåras sömlöst över olika implementeringstyper på din webbplats är den vanligaste orsaken att ID-tjänsten är felaktigt konfigurerad. Se till att varje implementeringstyp har samma Experience Cloud-ID (`mid`) på hela webbplatsen.
