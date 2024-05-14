---
title: XDM-objektvariabelmappning till Adobe Analytics
description: Visa vilka XDM-fält som Edge automatiskt mappar till analysvariabler.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 95c79a3085f87cbc1e28f14993f56feb4582a081
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 0%

---

# XDM-objektvariabelmappning till Adobe Analytics

Följande tabell visar de XDM-variabler som Adobe Experience Platform Edge Network automatiskt mappar till Adobe Analytics. Om du använder dessa sökvägar för XDM-fält behövs ingen ytterligare konfiguration för att skicka data till Adobe Analytics. Dessa fält ingår i **[!UICONTROL Adobe Analytics ExperienceEvent Template]** fältgrupp. Du bör använda dessa fält om du tänker skicka data till både Adobe Analytics och Adobe Experience Platform.

Om din organisation planerar att flytta till Customer Journey Analytics rekommenderar Adobe att du använder `data` objekt som skickar data direkt till Adobe Analytics utan att följa ett schema. Med den här strategin kan din organisation använda ditt eget schema i stället för att använda [!UICONTROL Adobe Analytics ExperienceEvent Template] (som inte är tillämpligt för Customer Journey Analytics). Se [Variabelmappning för dataobjekt till Adobe Analytics](data-var-mapping.md) för en liknande mappningstabell.

## Värdeprioriteringar

De flesta XDM-objektfälten i den här tabellen sammanfaller med en [dataobjektfält](data-var-mapping.md). Om du anger både ett givet XDM-objektfält och dess respektive dataobjektfält får dataobjektfältet prioritet. Om du använder både XDM-objektfältet och dataobjektfältet rekommenderar Adobe att du ställer in anpassade händelser med dataobjektfältet. Om fältet `data.__adobe.analytics.events` skriver den över alla XDM-objektfält som är relaterade till handel och anpassade händelser.

## Mappning av XDM-objektfält

Tidigare uppdateringar av tabellen finns på den här sidans [implementeringshistorik på GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md).

| Sökväg till XDM-fält | Analysvariabel och beskrivning |
| --- | --- |
| `xdm.application.isClose` | Hjälper till att definiera den mobila livscykelns mått [Krascher](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Hjälper till att avgöra när den mobila livscykelns mått ska höjas [Första starten](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | Hjälper till att avgöra när den mobila livscykelns mått ska höjas [Första starten](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Avgör om en close-händelse är en krasch eller inte. Giltiga värden är `close` (En livscykelsession avslutas och en pause-händelse togs emot för föregående session) och `unknown` (En livscykelsession avslutas utan en pause-händelse). Hjälper till att ställa in mätvärden för mobilens livscykel [Krascher](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) mätvärden. |
| `xdm.application.isInstall` | Den mobila livscykelns mått [Installationer](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | Den mobila livscykelns mått [Startar](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Hjälper till att ställa in den mobila livscykeldimensionen [Program-ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | Den mobila livscykelns mått [Uppgraderingar](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Hjälper till att ställa in den mobila livscykeldimensionen [Program-ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | Den mobila livscykelns mått [Längd på föregående session](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Utcheckningar](../../components/metrics/checkouts.md) mätvärden. |
| `xdm.commerce.checkouts.value` | Ökar [Utcheckningar](../../components/metrics/checkouts.md) mått med önskad mängd. |
| `xdm.commerce.order.currencyCode` | Anger [currencyCode](../vars/config-vars/currencycode.md) konfigurationsvariabel. |
| `xdm.commerce.order.purchaseID` | Anger [purchaseID](../vars/page-vars/purchaseid.md) sidvariabel. |
| `xdm.commerce.order.payments[0].transactionID` | Anger [transactionID](../vars/page-vars/transactionid.md) sidvariabel. |
| `xdm.commerce.productListAdds.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Cart Additions](../../components/metrics/cart-additions.md) mätvärden. |
| `xdm.commerce.productListAdds.value` | Ökar [Cart Additions](../../components/metrics/cart-additions.md) mätvärden. |
| `xdm.commerce.productListOpens.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Korgar](../../components/metrics/carts.md) mätvärden. |
| `xdm.commerce.productListOpens.value` | Ökar [Korgar](../../components/metrics/carts.md) mätvärden. |
| `xdm.commerce.productListRemovals.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Cart Removals](../../components/metrics/cart-removals.md) mätvärden. |
| `xdm.commerce.productListRemovals.value` | Ökar [Cart Removals](../../components/metrics/cart-removals.md) mätvärden. |
| `xdm.commerce.productListViews.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Vyer](../../components/metrics/cart-views.md) mätvärden. |
| `xdm.commerce.productListViews.value` | Ökar [Vyer](../../components/metrics/cart-views.md) mätvärden. |
| `xdm.commerce.productViews.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Produktvyer](../../components/metrics/product-views.md) mätvärden. |
| `xdm.commerce.productViews.value` | Ökar [Produktvyer](../../components/metrics/product-views.md) mätvärden. |
| `xdm.commerce.purchases.value` | Ökar [Beställningar](../../components/metrics/orders.md) mätvärden. |
| `xdm.device.model` | Den mobila livscykeldimensionen [Enhetsnamn](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Hjälper dig att ange [Färgdjup](../../components/dimensions/color-depth.md) dimension. |
| `xdm.device.screenHeight` | Hjälper dig att ange [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.screenWidth` | Hjälper dig att ange [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.type` | Typ av mobil enhet. |
| `xdm.environment.browserDetails.acceptLanguage` | Hjälper dig att ange [Språk](../../components/dimensions/language.md) dimension. |
| `xdm.environment.browserDetails.cookiesEnabled` | Anger [Cookie-stöd](../../components/dimensions/cookie-support.md) dimension. Giltiga värden är `Y` (webbläsaren accepterar cookies) och `N` (webbläsaren avvisar cookies). |
| `xdm.environment.browserDetails.javaEnabled` | Anger [Java aktiverat](../../components/dimensions/java-enabled.md) dimension. Giltiga värden är `Y` (Java är aktiverat) och `N` (Java är inaktiverat). |
| `xdm.environment.browserDetails.userAgent` | Används som reserv [unik besökare](../../components/metrics/unique-visitors.md) identifieringsmetod. Används vanligtvis med `User-Agent` HTTP-begärandehuvud. Du kan mappa det här fältet till en eVar om du vill använda det i rapporter. |
| `xdm.environment.browserDetails.viewportHeight` | Anger [Webbläsarhöjd](../../components/dimensions/browser-height.md) dimension. |
| `xdm.environment.browserDetails.viewportWidth` | Anger [Bredd på webbläsare](../../components/dimensions/browser-width.md) dimension. |
| `xdm.environment.carrier` | Den mobila livscykeldimensionen [Transportföretagets namn](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Hjälper dig att ange [Anslutningstyp](../../components/dimensions/connection-type.md) dimension. |
| `xdm.environment.ipV4` | Används som reserv [unik besökare](../../components/metrics/unique-visitors.md) identifieringsmetod. Används vanligtvis med `X-Forwarded-For` HTTP-huvud. |
| `xdm.environment.language` | Mobildimensionen Locale. |
| `xdm.environment.operatingSystem` | Den mobila livscykeldimensionen [Operativsystem](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Hjälper till att ställa in den mobila livscykeldimensionen [Operativsystemsversion](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Anger respektive [eVar](../../components/dimensions/evar.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Anger respektive [Hierarki](/help/components/dimensions/hierarchy.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Åsidosättning av avgränsare för listpropp. Det här fältet rekommenderas inte eftersom avgränsaren hämtas automatiskt från [Trafikvariabeladministratör](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) under rapportsvitens inställningar. Om du använder det här fältet kan det skapa en felmatchning mellan den avgränsare som används och den avgränsare som förväntas i Analytics. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | En strängarray som innehåller respektive [List Prop](../vars/page-vars/prop.md#list-props) värden. |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Sammanfogar alla `value` strängar i respektive `list[]` array till respektive [Listvariabel](../vars/page-vars/list.md). Avgränsaren väljs automatiskt baserat på det värde som anges i [Rapportsvitsinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Anger respektive [Prop](../../components/dimensions/prop.md) dimension. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till respektive [Anpassade händelser](../../components/metrics/custom-events.md) mätvärden. Varje händelse-ID finns i dess överordnade 100-grupp. Om du till exempel vill använda serialisering på `event678`, använda `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Ökar respektive [Anpassade händelser](../../components/metrics/custom-events.md) mått med önskad mängd. Varje händelse finns i dess överordnade 100-grupp. Fältet för `event567` är `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | The [Adobe Experience Cloud ID för identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| `xdm.marketing.trackingCode` | Anger [Spårningskod](../../components/dimensions/tracking-code.md) dimension. |
| `xdm.media.mediaTimed.completes.value` | Måtten för Media Analytics [Innehållet har slutförts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | Måtten för Media Analytics [Federerade data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | Måtten för Media Analytics [Förloppsmärke på 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | Måtten för Media Analytics [Vyer för innehållssegment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | Måtten för Media Analytics [Förloppsmärke på 5 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | Måtten för Media Analytics [Total pausvaraktighet](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | Måtten för Media Analytics [Pausa händelser](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`@id` | Media Analytics-dimensionen [Tillgångs-ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Media Analytics-dimensionen [Videonamn](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics-dimensionen [Originator](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics-dimensionen [Episod](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Media Analytics-dimensionen [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics-dimensionen [Innehållsklassificering](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics-dimensionen [Säsong](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics-dimensionen [Innehålls-ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics-dimensionen [Visa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`showType` | Media Analytics-dimensionen [Visa typ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Media Analytics-dimensionen [Videolängd](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Media Analytics-dimensionen [ID för mediesession](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Media Analytics-dimensionen [Innehållskanal](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Media Analytics-dimensionen [Innehållstyp](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Media Analytics-dimensionen [Nätverk](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Media Analytics-dimensionen [Innehållssegment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Media Analytics-dimensionen [Innehållsspelarens namn](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Media Analytics-dimensionen [SDK-version](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Media Analytics-dimensionen [Medieflödestyp](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Media Analytics-dimensionen [Strömformat](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | Måtten för Media Analytics [Tio % statusmarkör](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | Måtten för Media Analytics [95 % förloppsmärke](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `xdm.media.mediaTimed.resumes.value` | Måtten för Media Analytics [Återuppta innehåll](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | Måtten för Media Analytics [Media börjar](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | Måtten för Media Analytics [Sjuttiofem % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | Måtten för Media Analytics [Innehållstid](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | Måtten för Media Analytics [Medietid tillagd](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | Besökarens latitud. Hjälpuppsättning [Plats för mobil livscykel](/help/components/dimensions/lifecycle-dimensions.md) dimensioner. |
| `xdm.placeContext.geo._schema.longitude` | Besökarens longitud. Hjälpuppsättning [Plats för mobil livscykel](/help/components/dimensions/lifecycle-dimensions.md) dimensioner. |
| `xdm.placeContext.geo.postalCode` | The [Postnummer](../../components/dimensions/zip-code.md) dimension. |
| `xdm.placeContext.geo.stateProvince` | The [USA](../../components/dimensions/us-states.md) dimension. |
| `xdm.placeContext.localTime` | Visas som `t_time_info` in [Dataflöden](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Gäller [produktsyntax](../vars/page-vars/products.md) försäljning till eVars. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Gäller [produktsyntax](../vars/page-vars/products.md) försäljning till event. |
| `xdm.productListItems[].productCategories[].categoryID` | The [Kategori](../../components/dimensions/category.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `xdm.productListItems[].name` | The [Produkt](../../components/dimensions/product.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. If `xdm.productListItems[].SKU` och `xdm.productListItems[].name` båda innehåller data, värdet i `xdm.productListItems[].SKU` används. |
| `xdm.productListItems[].priceTotal` | Hjälper till att avgöra [Intäkter](../../components/metrics/revenue.md) mätvärden. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `xdm.productListItems[].quantity` | Hjälper till att avgöra [Enheter](../../components/metrics/units.md) mätvärden. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `xdm.productListItems[].SKU` | The [Produkt](../../components/dimensions/product.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. If `xdm.productListItems[].SKU` och `xdm.productListItems[].name` båda innehåller data, värdet i `xdm.productListItems[].SKU` används. |
| `xdm.web.webInteraction.URL` | The [linkURL](../vars/config-vars/linkurl.md) implementeringsvariabel. |
| `xdm.web.webInteraction.name` | The [Egen länk](../../components/dimensions/custom-link.md), [Hämta länk](../../components/dimensions/download-link.md), eller [Avsluta länk](../../components/dimensions/exit-link.md) dimension, beroende på värdet i `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Anger vilken typ av länk som klickas. Giltiga värden är `other` (Anpassade länkar), `download` (Hämta länkar) och `exit` (Avsluta länkar). |
| `xdm.web.webPageDetails.URL` | The [Sidans URL](../../components/dimensions/page-url.md) dimension. |
| `xdm.web.webPageDetails.isErrorPage` | Flagga som hjälper till att fastställa &quot;Sidor som inte hittas&quot; [dimension](../../components/dimensions/pages-not-found.md) och [mått](../../components/metrics/pages-not-found.md). |
| `xdm.web.webPageDetails.name` | The [Sida](../../components/dimensions/page.md) dimension. |
| `xdm.web.webPageDetails.server` | The [Server](../../components/dimensions/server.md) dimension. |
| `xdm.web.webPageDetails.siteSection` | The [Platsavsnitt](../../components/dimensions/site-section.md) dimension. |
| `xdm.web.webReferrer.URL` | The [Referent](../../components/dimensions/referrer.md) dimension. |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappa andra XDM-fält till analysvariabler

Om det finns mått eller mätvärden som du vill lägga till i Adobe Analytics kan du göra det genom [Kontextdatavariabler](../vars/page-vars/contextdata.md).

### Implicit mappning

Alla XDM-fältelement som inte mappas automatiskt skickas till Adobe Analytics som kontextdata med prefixet `a.x.` Du kan sedan mappa den här kontextvariabeln till den önskade Analytics-variabeln med [Bearbetar regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html). Om du till exempel skickar följande händelse:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

Web SDK skickar dessa data till Adobe Analytics som kontextdatavariabel `a.x._atag.search.term`. Du kan sedan använda en bearbetningsregel för att tilldela det kontextdatavariabelvärdet till den önskade analysvariabeln, till exempel ett `eVar`:

![Bearbetningsregel för sökterm](assets/examplerule.png)

## Explicit mappning

Du kan också mappa XDM-fältelement explicit som kontextdata. Alla XDM-fältelement som uttryckligen mappas med `contextData` skickas till Adobe Analytics som kontextdata utan prefix. Du kan sedan mappa den här kontextvariabeln till den önskade Analytics-variabeln med [Bearbetar regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html). Om du till exempel skickar följande händelse:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

Web SDK skickar dessa data till Adobe Analytics som kontextdatavariabel `somevalue` med värde `1`.  Du kan sedan använda en bearbetningsregel för att tilldela det kontextdatavariabelvärdet till den önskade analysvariabeln, till exempel ett `eVar`:

![Bearbetningsregel för sökterm](assets/examplerule-explicit.png)
