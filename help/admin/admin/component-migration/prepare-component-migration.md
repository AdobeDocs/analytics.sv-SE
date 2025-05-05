---
description: Beskriver de förberedelser som krävs för att förbereda migrering av komponenter och projekt från Adobe Analytics till Customer Journey Analytics.
title: Förbereda för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 1%

---

# Förbereda för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics

Innan någon i organisationen börjar migrera projekt enligt beskrivningen i [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md) ska du slutföra följande avsnitt.

## Förutsättningar

Innan dina projekt och tillhörande komponenter är klara att migreras måste du följa stegen i [Utveckla från Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=sv-SE) i Adobe Customer Journey Analytics Guide. De här stegen omfattar:

1. Använd någon av följande metoder för att importera data till Adobe Experience Platform för att visa Adobe Analytics rapportsvitdata i Customer Journey Analytics:

   >[!NOTE]
   >
   >  När du använder WebSDK för att importera data måste alla schemafält mappas manuellt. (Mer information om mappningsprocessen finns i [Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * Om du vill använda Adobe Analytics källanslutning måste du:

      1. [Konfigurera rapportsviter för förtäring i Adobe Experience Platform och Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=sv-SE#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Importera och använd data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=sv-SE)

   * Om du vill använda WebSDK måste du:

      1. [Konfigurera rapportsviter för förtäring i Adobe Experience Platform och Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=sv-SE#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Infoga data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html?lang=sv-SE)

1. Skapa en [anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=sv-SE) och [datavy](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=sv-SE) med inkapslade data.

1. Se till att användare i Customer Journey Analytics är tilldelade datavyer där data mappas.

   Mer information finns i [Customer Journey Analytics behörigheter i åtkomstkontrollen Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=sv-SE#customer-journey-analytics-permissions-in-admin-console) i [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=sv-SE).

   Fliken Behörigheter ingår i varje produktprofil i Admin Console. Du kan lägga till användare i specifika produktprofiler. Sedan tilldelar du rättigheter till specifika datavyer och anger vilka behörigheter användarna i en produktprofil har.

1. Bestäm som organisation hur du ska mappa komponenter.

   Mer information finns i avsnittet nedan, [Bestäm hur du ska mappa komponenter](#decide-as-an-organization-how-you-will-map-components).

## Förstå vad som ingår i en migrering

I följande tabeller visas vilka element i ett projekt och en komponent som ingår i en migrering:

### Komponentelement som migreras

Dimensioner och mätvärden migreras som en del av mappningsprocessen som beskrivs i [Migrera Adobe Analytics-projekt till Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Segment, datumintervall och beräknade värden som inte redan finns i Customer Journey Analytics återskapas där baserat på de dimensioner och mått som mappas.

|  | Migrerad |
|---------|---------|
| **[Ägare](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimensioner och mätvärden: Nej<p>Segment och datumintervall: ![bock](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Delar](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensioner och mätvärden: Nej<p>Segment och datumintervall: Nej</p> |
| **[Beskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensioner och mätvärden: Nej<p>Segment och datumintervall: ![bock](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Taggar](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensioner och mätvärden: Nej<p>Segment och datumintervall: Nej</p> |
| **[Attribution (på dimensioner)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensioner och mätvärden: Nej<p>Segment och datumintervall: Nej</p> |

{style="table-layout:auto"}

### Projektelement som migreras

|  | Migrerad |
|---------|----------|
| **[Datumintervall](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Segment](/help/components/segmentation/seg-overview.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensioner](/help/components/dimensions/overview.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) har mappats automatiskt eller manuellt |
| **[Mätvärden](/help/components/metrics/overview.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) har mappats automatiskt eller manuellt |
| **[Paneler](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Ägare](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![bockmarkering](assets/Smock_Checkmark_18_N.svg) Definierad av den användare som utför migreringen |
| **[Kuration](/help/analyze/analysis-workspace/curate-share/curate.md)** | Nej |
| **[Delar](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Nej |
| **[Anteckningar](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Nej |
| **[Mappstruktur](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Nej |
| **[Beskrivningar](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |
| **[Taggar](/help/analyze/landing.md)** | Nej |
| **[Favoriter](/help/analyze/landing.md)** | Nej |
| **[Scheman](/help/components/scheduled-projects-manager.md)** | Nej |
| **[Avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![bock](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Förstå element som inte stöds och som orsakar fel

Följande visualiseringar och paneler stöds inte i Customer Journey Analytics. När dessa element ingår i ett projekt före migreringen kan de antingen göra att migreringen misslyckas eller orsaka fel efter att projektet har migrerats.

Ta bort dessa element från Adobe Analytics-projektet innan du migrerar projektet till Customer Journey Analytics. Om en migrering misslyckas tar du bort de här elementen innan du försöker migrera igen.

### Visualiseringar som inte stöds

* [Karta](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### Paneler som inte stöds

* [Analyser för mål (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Segmentjämförelse](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Medie - genomsnittlig minutmålgrupp](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Nästa eller föregående objekt](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Sidsammanfattning](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Bidragsanalys](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## Bestäm som organisation hur du ska mappa komponenter

>[!IMPORTANT]
>
>Migreringsprocessen identifierar komponenter i ditt Adobe Analytics-projekt som inte kan mappas automatiskt till komponenter i Customer Journey Analytics och gör att du kan mappa dem manuellt.
>
>**Alla mappningar som görs i ett projekt gäller för alla framtida projekt i hela IMS-organisationen, oavsett vilken användare som utför migreringen. Dessa mappningar kan inte ändras eller ångras förutom genom att kontakta kundtjänst.**
>
>Därför är det viktigt att organisationen bestämmer hur dimensioner och mått mappas innan några projekt migreras. På så sätt undviker du att enskilda administratörer fattar beslut i en silo när de endast överväger ett enskilt projekt.
>
>Här följer en lista med mått och mätvärden som du måste mappa manuellt om de finns i ditt projekt. Vi rekommenderar att du granskar den här listan innan du migrerar. Om någon av dessa komponenter finns i ditt projekt, bestämmer du nu vilka Customer Journey Analytics-komponenter du ska mappa dem till.


### Dimensioner som måste mappas manuellt

* genomsnittstid
* pagetimeseconds
* singlepagevisier
* visitnummer
* timeBefore
* tidsspenderad
* kategori
* anslutningstyp
* kundlojalitet
* anpassad länk
* nedladdningslänk
* exitlink
* hitdepth
* hittype
* banlängd
* dagar före första köp
* dagsincelastpurchase
* dagsinsbesök
* IDtatementState
* optoutreason
* persistentcookie
* returfrekvens
* sökmotorinenatural
* sökmotorinenaturnyckelord
* mobiloperatör
* skärmupplösning
* surveyBase
* försiktighetsåtgärder
* tbase
* målraw


### Mätvärden som måste mappas manuellt

* timespentbesök
* timespentvisitor
* omladdningar
* studsar
* bouncert
* pageevents
* pageviewspervisit
* orderspervisit
* medelsiddjup
* averagetimespentonsite
* exitlinkinstances
* anpassade länkinstanser
* downloadlinkinstances
* mörka besökare
* singlepagevisier
* singlevalusivs
* besökshemsida
* visitorsmcvisid
* pagesnot hittades
* nya ärenden
* tid_granularitet
* concurrent_viewers_visits
* concurrent_viewers_instances
* enheter
* uppskattade personer
* playback_time_used_seconds
* playback_time_used_minutes
* medelhög_minut_målgrupp_tid_baserad
* medelhög_minut_målgrupp_media_tid
* medelhög_minut_målgrupp_innehållstid
* video_length
* målkonvertering
* targetTimpression
