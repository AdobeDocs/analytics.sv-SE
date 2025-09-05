---
description: Du kan aktivera media i Analytics för att reservera en särskild uppsättning medielösningsvariabler som kan användas för mätning och rapportering.
title: Mediehantering
feature: Admin Tools
uuid: a841a5a8-6d47-478d-b02b-6c1647fb04ce
exl-id: b6dc8d93-3f89-4671-a4c3-18614667bf4e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Mediehantering

Du kan använda det här gränssnittet för att reservera variabler som ska användas i mediemätningar och -rapporter. När dessa variabler beter sig på liknande sätt som eVars, props och events, men inte räknas med i några variabelgränser. När de har aktiverats visas en ny uppsättning medierapporter på Analytics-menyerna.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Media Management]**.

Följande alternativ för mediehantering är tillgängliga när du redigerar en rapportserie:

* [!UICONTROL **Medierapportering**]

  Använd de här kryssrutorna om du vill aktivera mått och mätvärden för direktuppspelande medietjänster.

   * [Mediekärndimensioner](/help/components/dimensions/sm-core.md)
   * [Media core metrics](/help/components/metrics/sm-core.md)
   * [Media och dimensioner](/help/components/dimensions/sm-ads.md)
   * [Mått för mediereklam](/help/components/metrics/sm-ads.md)
   * [Mediekapiteldimensioner](/help/components/dimensions/sm-chapters.md)
   * [Mediekapitelmått](/help/components/metrics/sm-chapters.md)
   * [Mått för mediakvalitet](/help/components/dimensions/sm-quality.md)
   * [Mätvärden för mediakvalitet](/help/components/metrics/sm-quality.md)
   * [Metadata för video](/help/components/dimensions/sm-video-metadata.md)
   * [Metadata för video](/help/components/metrics/sm-video-metadata.md)
   * [Dimensioner för ljudmetadata](/help/components/dimensions/sm-audio-metadata.md)
   * [Mätvärden för spårning av spelartillstånd](/help/components/metrics/sm-player-state.md)

* [!UICONTROL **Medieklassificeringar**]

  Specifika klassificeringar för dimensioner för direktuppspelande medietjänster finns på sidan [!UICONTROL Media Classifications]. De fungerar ungefär som [konverteringsklassificeringar](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md) som är tillgängliga för konverteringsvariabler. Om du aktiverar vissa komponenter under [!UICONTROL Media Reporting] skapas klassificeringsdimensioner automatiskt. Du kan använda det här gränssnittet för att skapa egna klassificeringsdimensioner eller överföra klassificeringsdata.

Allmän information om hur du integrerar direktuppspelningsmediedata i Adobe Analytics finns i [Översikt över Adobe direktuppspelningsmedietjänster](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview).
