---
title: Variabelmappning i analyser i Adobe Experience Edge
description: Visa vilka XDM-fält som Edge automatiskt mappar till analysvariabler.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variabelmappning i analyser i Adobe Experience Edge

Följande tabell visar de variabler som Adobe Experience Platform Edge Network automatiskt mappar till Adobe Analytics. Om du använder dessa XDM-fältsökvägar behövs ingen ytterligare konfiguration för att skicka data till Adobe Analytics.

| Sökväg till XDM-fält | Analysdimension och beskrivning |
| --- | --- |
| `application.isClose` | Hjälper till att definiera mobilmåtten [Krascher](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isInstall` | Hjälper till att avgöra när de mobila mätvärdena ska höjas [Första starten](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Hjälper till att avgöra när de mobila mätvärdena ska höjas [Första starten](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Avgör om en close-händelse är en krasch eller inte. Giltiga värden är `close` (En livscykelsession avslutas och en pause-händelse togs emot för föregående session) och `unknown` (En livscykelsession avslutas utan en pause-händelse). Hjälper dig att ange [Krascher](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics) mätvärden. |
| `application.isInstall` | Det mobila måttet [Installationer](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Det mobila måttet [Startar](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Hjälper till att ange mobildimensionen [Program-ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isUpgrade` | Det mobila måttet [Uppgraderingar](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Hjälper till att ange mobildimensionen [Program-ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | Det mobila måttet [Längd på föregående session](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Utcheckningar](../../components/metrics/checkouts.md) mätvärden. |
| `commerce.checkouts.value` | Ökar [Utcheckningar](../../components/metrics/checkouts.md) mått med önskad mängd. |
| `commerce.order.currencyCode` | Anger [currencyCode](../vars/config-vars/currencycode.md) konfigurationsvariabel. |
| `commerce.order.purchaseID` | Anger [purchaseID](../vars/page-vars/purchaseid.md) sidvariabel. |
| `commerce.order.transactionID` | Anger [transactionID](../vars/page-vars/transactionid.md) sidvariabel. |
| `commerce.productListAdds.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Cart Additions](../../components/metrics/cart-additions.md) mätvärden. |
| `commerce.productListAdds.value` | Ökar [Cart Additions](../../components/metrics/cart-additions.md) mätvärden. |
| `commerce.productListOpens.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Korgar](../../components/metrics/carts.md) mätvärden. |
| `commerce.productListOpens.value` | Ökar [Korgar](../../components/metrics/carts.md) mätvärden. |
| `commerce.productListRemovals.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Cart Removals](../../components/metrics/cart-removals.md) mätvärden. |
| `commerce.productListRemovals.value` | Ökar [Cart Removals](../../components/metrics/cart-removals.md) mätvärden. |
| `commerce.productListViews.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Vyer](../../components/metrics/cart-views.md) mätvärden. |
| `commerce.productListViews.value` | Ökar [Vyer](../../components/metrics/cart-views.md) mätvärden. |
| `commerce.productViews.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till [Produktvyer](../../components/metrics/product-views.md) mätvärden. |
| `commerce.productViews.value` | Ökar [Produktvyer](../../components/metrics/product-views.md) mätvärden. |
| `commerce.purchases.value` | Ökar [Beställningar](../../components/metrics/orders.md) mätvärden. |
| `device.model` | Den mobila dimensionen [Enhetsnamn](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.colorDepth` | Hjälper dig att ange [Färgdjup](../../components/dimensions/color-depth.md) dimension. |
| `device.screenHeight` | Hjälper dig att ange [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md) dimension. |
| `device.screenWidth` | Hjälper dig att ange [Bildskärmsupplösning](../../components/dimensions/monitor-resolution.md) dimension. |
| `device.type` | Typ av mobil enhet. |
| `environment.browserDetails.acceptLanguage` | Hjälper dig att ange [Språk](../../components/dimensions/language.md) dimension. |
| `environment.browserDetails.cookiesEnabled` | Anger [Cookie-stöd](../../components/dimensions/cookie-support.md) dimension. Giltiga värden är `Y` (webbläsaren accepterar cookies) och `N` (webbläsaren avvisar cookies). |
| `environment.browserDetails.javaEnabled` | Anger [Java aktiverat](../../components/dimensions/java-enabled.md) dimension. Giltiga värden är `Y` (Java är aktiverat) och `N` (Java är inaktiverat). |
| `environment.browserDetails.userAgent` | Används som reserv [unik besökare](../../components/metrics/unique-visitors.md) identifieringsmetod. Används vanligtvis med `User-Agent` HTTP-begärandehuvud. Du kan mappa det här fältet till en eVar om du vill använda det i rapporter. |
| `environment.browserDetails.viewportHeight` | Anger [Webbläsarhöjd](../../components/dimensions/browser-height.md) dimension. |
| `environment.browserDetails.viewportWidth` | Anger [Bredd på webbläsare](../../components/dimensions/browser-width.md) dimension. |
| `environment.carrier` | Den mobila dimensionen [Transportföretagets namn](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Hjälper dig att ange [Anslutningstyp](../../components/dimensions/connection-type.md) dimension. |
| `environment.ipV4` | Används som reserv [unik besökare](../../components/metrics/unique-visitors.md) identifieringsmetod. Används vanligtvis med `X-Forwarded-For` HTTP-huvud. |
| `environment.language` | Mobildimensionen Locale. |
| `environment.operatingSystem` | Den mobila dimensionen [Operativsystem](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | Hjälper dig att ange [Operativsystemsversion](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions) dimension. |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Anger respektive [eVar](../../components/dimensions/evar.md) dimension. |
| `_experience.analytics.customDimensions.`<br/>`hierarchies.hier1` -<br/>`_experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Anger respektive [Hierarki](/help/components/dimensions/hierarchy.md) dimension. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Åsidosättning av avgränsare för listpropp. Det här fältet rekommenderas inte eftersom avgränsaren hämtas automatiskt från [Trafikvariabeladministratör](/help/admin/admin/c-traffic-variables/traffic-var.md) under rapportsvitens inställningar. Om du använder det här fältet kan det skapa en felmatchning mellan den avgränsare som används och den avgränsare som förväntas i Analytics. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | En strängarray som innehåller respektive [List Prop](../vars/page-vars/prop.md#list-props) värden. |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Sammanfogar alla `value` strängar i respektive `list[]` array till respektive [Listvariabel](../vars/page-vars/list.md). Avgränsaren väljs automatiskt baserat på det värde som anges i [Rapportsvitsinställningar](/help/admin/admin/conversion-var-admin/list-var-admin.md). |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Anger respektive [Prop](../../components/dimensions/prop.md) dimension. |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Gäller [händelseserialisering](../vars/page-vars/events/event-serialization.md) till respektive [Anpassade händelser](../../components/metrics/custom-events.md) mätvärden. |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Ökar respektive [Anpassade händelser](../../components/metrics/custom-events.md) mått med önskad mängd. |
| `identityMap.ECID[0].id` | The [Adobe Experience Cloud ID för identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| `marketing.trackingCode` | Anger [Spårningskod](../../components/dimensions/tracking-code.md) dimension. |
| `media.mediaTimed.completes.value` | Måtten för Media Analytics [Innehållet har slutförts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | Måtten för Media Analytics [Federerade data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | Måtten för Media Analytics [Förloppsmärke på 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | Måtten för Media Analytics [Vyer för innehållssegment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | Måtten för Media Analytics [Förloppsmärke på 5 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | Måtten för Media Analytics [Total pausvaraktighet](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | Måtten för Media Analytics [Pausa händelser](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Media Analytics-dimensionen [Tillgångs-ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Media Analytics-dimensionen [Videonamn](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics-dimensionen [Originator](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics-dimensionen [Episod](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Media Analytics-dimensionen [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics-dimensionen [Innehållsklassificering](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics-dimensionen [Säsong](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics-dimensionen [Innehålls-ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics-dimensionen [Visa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Media Analytics-dimensionen [Visa typ](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Media Analytics-dimensionen [Videolängd](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Media Analytics-dimensionen [ID för mediesession](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Media Analytics-dimensionen [Innehållskanal](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Media Analytics-dimensionen [Innehållstyp](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Media Analytics-dimensionen [Nätverk](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Media Analytics-dimensionen [Innehållssegment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Media Analytics-dimensionen [Innehållsspelarens namn](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Media Analytics-dimensionen [SDK-version](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Media Analytics-dimensionen [Medieflödestyp](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Media Analytics-dimensionen [Strömformat](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | Måtten för Media Analytics [Tio % statusmarkör](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | Måtten för Media Analytics [95 % förloppsmärke](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | Måtten för Media Analytics [Återuppta innehåll](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | Måtten för Media Analytics [Media börjar](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | Måtten för Media Analytics [Sjuttiofem % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | Måtten för Media Analytics [Innehållstid](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | Måtten för Media Analytics [Medietid tillagd](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | Den mobila dimensionen Latitude. |
| `placeContext.geo.longitude` | Den mobila dimensionens longitud. |
| `placeContext.geo.postalCode` | The [Postnummer](../../components/dimensions/zip-code.md) dimension. |
| `placeContext.geo.stateProvince` | The [USA](../../components/dimensions/us-states.md) dimension. |
| `placeContext.localTime` | Hjälper till att fylla i [Tidszoner](/help/analyze/reports-analytics/reports.md) i Rapport och analys. Visas som `t_time_info` in [Dataflöden](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Gäller [produktsyntax](../vars/page-vars/products.md) försäljning till eVars. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Gäller [produktsyntax](../vars/page-vars/products.md) försäljning till event. |
| `productListItems[].lineItemId` | The [Kategori](../../components/dimensions/category.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `productListItems[].name` | The [Produkt](../../components/dimensions/product.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. If `productListItems[].SKU` och `productListItems[].name` båda innehåller data, värdet i `productListItems[].SKU` används. |
| `productListItems[].priceTotal` | Hjälper till att avgöra [Intäkter](../../components/metrics/revenue.md) mätvärden. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `productListItems[].quantity` | Hjälper till att avgöra [Enheter](../../components/metrics/units.md) mätvärden. Se även [produkter](../vars/page-vars/products.md) sidvariabel. |
| `productListItems[].SKU` | The [Produkt](../../components/dimensions/product.md) dimension. Se även [produkter](../vars/page-vars/products.md) sidvariabel. If `productListItems[].SKU` och `productListItems[].name` båda innehåller data, värdet i `productListItems[].SKU` används. |
| `web.webInteraction.URL` | The [linkURL](../vars/config-vars/linkurl.md) implementeringsvariabel. |
| `web.webInteraction.name` | The [Egen länk](../../components/dimensions/custom-link.md), [Hämta länk](../../components/dimensions/download-link.md), eller [Avsluta länk](../../components/dimensions/exit-link.md) dimension, beroende på värdet i `web.webInteraction.type` |
| `web.webInteraction.type` | Anger vilken typ av länk som klickas. Giltiga värden är `other` (Anpassade länkar), `download` (Hämta länkar) och `exit` (Avsluta länkar). |
| `web.webPageDetails.URL` | The [Sidans URL](../../components/dimensions/page-url.md) dimension. |
| `web.webPageDetails.errorPage` | Flagga som hjälper till att fastställa &quot;Sidor som inte hittas&quot; [dimension](../../components/dimensions/pages-not-found.md) och [mått](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | The [Sida](../../components/dimensions/page.md) dimension. |
| `web.webPageDetails.server` | The [Server](../../components/dimensions/server.md) dimension. |
| `web.webPageDetails.siteSection` | The [Platsavsnitt](../../components/dimensions/site-section.md) dimension. |
| `web.webReferrer.URL` | The [Referent](../../components/dimensions/referrer.md) dimension. |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappa andra XDM-fält till analysvariabler

Om det finns mått eller mätvärden som du vill lägga till i Adobe Analytics kan du göra det genom [Kontextdatavariabler](../vars/page-vars/contextdata.md). Alla XDM-fältelement som inte mappas automatiskt skickas till Adobe Analytics som kontextdata med prefixet a.x. Du kan sedan mappa den här kontextvariabeln till den önskade Analytics-variabeln med [Bearbetar regler](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=en). Om du till exempel skickar följande händelse:

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

Web SDK skickar dessa data till Adobe Analytics som kontextdatavariabel `a.x._atag.search.term`. Du kan sedan använda en bearbetningsregel för att tilldela det kontextdatavariabelvärdet till den önskade analysvariabeln, till exempel en eVar:

![Bearbetningsregel för sökterm](assets/examplerule.png)
