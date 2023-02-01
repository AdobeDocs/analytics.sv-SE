---
title: Implementera Adobe Analytics med Adobe Experience Platform Web SDK
description: Använd Web SDK-tillägget i Adobe Experience Platform Data Collection för att skicka data till Adobe Analytics.
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 1%

---

# Implementera Adobe Analytics med Adobe Experience Platform Web SDK

Du kan använda [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) för att skicka data till Adobe Analytics. Den här implementeringsmetoden fungerar genom att översätta [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv) till ett format som används av Analytics.

Du kan skicka data till Experience Edge direkt med Web SDK eller via Web SDK-tillägget i Taggar.

## Web SDK

Översikt över implementeringsuppgifterna:

![Implementera Adobe Analytics med Web SDK-arbetsflöde](../../assets/websdk-annotated.png)

|<div style="width:20px"></div>| Aktivitet | Mer information | |-| —|—| | 1 | Kontrollera att du har **har definierat en rapportserie**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Konfigurera scheman och datauppsättningar**. För att standardisera datainsamlingen för användning i olika program som utnyttjar Adobe Experience Platform har Adobe skapat den öppna och offentligt dokumenterade standarden Experience Data Model (XDM). | [Översikt över schemaanvändargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) och [Översikt över användargränssnittet för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en) | | 3 | **Skapa ett datalager** för att hantera spårning av data på din webbplats. | [Skapa ett datalager](../../prepare/data-layer.md) | | 4 | **Installera den fördefinierade fristående versionen**. Du kan referera till biblioteket (`alloy.js`) på CDN direkt på din sida eller ladda ned och lagra den i din egen infrastruktur. Du kan också använda NPM-paketet. | [Installera den fördefinierade fristående versionen](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) och [Använda NPM-paketet](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **Konfigurera ett datastream**. En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web SDK implementeras. | [Konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Lägg till en Adobe Analytics-tjänst** till din datastream. Tjänsten styr om och hur data skickas till Adobe Analytics. | [Lägg till Adobe Analytics-tjänst i ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Konfigurera Web SDK**. Se till att biblioteket som du installerade i steg 4 är korrekt konfigurerat med dataStream ID (kallades tidigare edge configuration id (`edgeConfigId`)), organisations-ID (`orgId`) och andra tillgängliga alternativ. | [Konfigurera Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) | | 8 | **Kör kommandon** och/eller **spåra händelser**. När baskoden har implementerats på webbsidan kan du börja köra kommandon och spåra händelser med SDK. | [Kör kommandon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) och [Spåra händelser](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **Utöka och validera implementeringen** innan det går till produktion. | |



## Web SDK-tillägg

Översikt över implementeringsuppgifterna:

![Implementera Adobe Analytics med hjälp av arbetsflödet för Web SDK-tillägg](../../assets/websdk-extension-annotated.png)

|<div style="width:20px"></div> | Aktivitet | Mer information | |-| —|—| | 1 | Kontrollera att du har **har definierat en rapportserie**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Konfigurera scheman och datauppsättningar**. För att standardisera datainsamlingen för användning i olika program som utnyttjar Adobe Experience Platform har Adobe skapat den öppna och offentligt dokumenterade standarden Experience Data Model (XDM). | [Översikt över schemaanvändargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) och [Översikt över användargränssnittet för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en) | | 3 | **Skapa ett datalager** för att hantera spårning av data på din webbplats. | [Skapa ett datalager](../../prepare/data-layer.md) | | 4 | **Konfigurera ett datastream**. En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web SDK implementeras. | [Konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Lägg till en Adobe Analytics-tjänst** till din datastream. Tjänsten styr om och hur data skickas till Adobe Analytics. | [Lägg till Adobe Analytics-tjänst i ett datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **Skapa en taggegenskap**. Egenskaper är överliggande behållare som används för att referera till tagghanteringsdata.| [Skapa eller konfigurera en taggegenskap för webben](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Installera och konfigurera Web SDK-tillägget** i taggegenskapen. Konfigurera Web SDK-tillägget för att skicka data till den dataström som konfigurerats i steg 4. | [Adobe Experience Platform Web SDK-tillägg - översikt](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **Upprepa, validera och publicera** till produktion. Lägg till taggegenskapen på din webbplats. Använd sedan dataelement, regler och så vidare för att anpassa implementeringen. | [Översikt över publicering](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) |



## Ytterligare resurser

Taggar kan anpassas mycket. Läs mer om hur du får ut mesta möjliga av Adobe Analytics genom att inkludera rätt data i implementeringen.

- [Dokumentation för taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Lär dig hur gränssnittet fungerar och vilka tillägg som är tillgängliga.

- [Adobe Experience Platform Web SDK-dokumentation](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en)
