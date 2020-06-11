---
title: Rapporter
description: Dimensionerna och måtten som Rapporter och analyser använder för varje rapport.
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 0%

---


# Rapporter

Varje rapport i Rapporter och analyser använder en dedikerad dimension och standardmått. Du kan ändra måtten i varje rapport och lägga till uppdelningar om du vill. I följande listor visas vilken dimension som används i varje rapport.

> [!NOTE] Din rapportmeny kan se annorlunda ut beroende på vilka anpassningar en administratör i organisationen har gjort. Se [Menyanpassning](/help/admin/admin/customize-menus.md) i användarhandboken för Admin.

## Webbplatsmått

Innehåller rapporter som vanligtvis trendar med ett datumintervall. Innehåller också unika rapporter, till exempel rekommenderade rapporter och realtidsrapporter.

* Mina rekommenderade rapporter: Skapar en kontrollpanel som innehåller flera rapporter för omedelbar information.
* Nyckeltal: En rapport som gör det möjligt att trender upp till fem mätvärden i taget. Trender [Sidvyer](/help/components/metrics/page-views.md), [besök](/help/components/metrics/visits.md)och [unika besökare](/help/components/metrics/unique-visitors.md) som standard.
* Sidvyer: Trends the [Page views](/help/components/metrics/page-views.md) metric over time.
* Besök: Trends the [Visits](/help/components/metrics/visits.md) metric over time.
* Besökare: Trender över olika [unika besökarmått](/help/components/metrics/unique-visitors.md) över tid.
   * Unika besökare: Räknar endast besökare en gång för hela det valda datumintervallet.
   * unika besökare varje timme: Räknar besökare flera gånger om de besöker under olika timmar av det valda datumintervallet.
   * Dagliga unika besökare: Räknar besökare flera gånger om de besöker under olika dagar i det valda datumintervallet.
   * unika besökare varje vecka: Räknar besökare flera gånger om de besöker under olika veckor i det valda datumintervallet.
   * unika besökare varje månad: Räknar besökare flera gånger om de besöker under olika månader i det valda datumintervallet.
   * Kvartalsvisa unika besökare: Räknar besökare flera gånger om de besöker under olika kvartal av det valda datumintervallet. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Unika besökare varje år: Räknar besökare flera gånger om de besöker under olika kalenderår i det valda datumintervallet.
* Tid per besök: Använder [tidsåtgången per besök - fast](/help/components/dimensions/time-spent-per-visit.md) dimension.
* Tid före händelse: Använder [Tid före](/help/components/dimensions/time-prior-to-event.md) händelsedimension.
* Inköp: Innehåller rapporter om inköpsbaserade mätvärden.
   * Inköpskonverteringstratt: Rapport om [besök](/help/components/metrics/visits.md), [kundvagnar](/help/components/metrics/carts.md), [beställningar](/help/components/metrics/orders.md), [intäkter](/help/components/metrics/revenue.md)och [enheter](/help/components/metrics/units.md) i en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Intäkter: Trends the metric [Revenue](/help/components/metrics/revenue.md) over time.
   * Beställningar: Trends the metric [Orders](/help/components/metrics/orders.md) over time.
   * Enheter: Trends the metric [Units](/help/components/metrics/units.md) over time.
* Kundvagn: Innehåller rapporter om kundvagnsstatistik.
   * Konverteringsfunktion för kundvagn: Rapporterar [instanser](/help/components/metrics/instances.md), [kundvagnar](/help/components/metrics/carts.md), [utcheckningar](/help/components/metrics/checkouts.md), [beställningar](/help/components/metrics/orders.md)och [intäkter](/help/components/metrics/revenue.md) i en trattrapport.
   * Kartor: Trends the metric [Carts](/help/components/metrics/carts.md) over time.
   * Vyer: Trends the metric [Cart views](/help/components/metrics/cart-views.md) over time.
   * Kundvagnstillägg: Trends the metric [Cart additions](/help/components/metrics/cart-additions.md) over time.
   * Borttagning av kundvagn: Trends the metric [Cart removals](/help/components/metrics/cart-removals.md) over time.
   * Utcheckningar: Trends the metric [Checkouts](/help/components/metrics/checkouts.md) over time.
* Anpassade händelser: Innehåller alla rapporter om anpassade [händelser](/help/components/metrics/custom-events.md) som är specifika för implementeringen.
* Börjor: Visar robotrelaterade rapporter.
   * Börjor: Visar de botar som oftast finns på webbplatsen. Se [Punktregler](../../admin/admin/bot-removal/bot-rules.md) i användarhandboken för Admin.
   * Punktsidor: Visar de sidor som träffar mest.
* Realtid: Visar vissa mått och mätvärden inom några sekunder efter datainsamlingen. Mer information finns i [Realtidsrapporter](/help/components/c-real-time-reporting/realtime.md) .

## Webbplatsinnehåll

Innehåller rapporter om dimensioner som vanligtvis visar webbplatsinnehåll. Du kan använda klassificeringar i vissa av dessa rapporter. Att använda klassificeringar innebär att en rapport blir en meny som innehåller källrapporten och klassificeringsrapporterna.

* Sidor: Använder dimensionen [Sida](/help/components/dimensions/page.md) .
* Site section: Använder dimensionen för [platsavsnittet](/help/components/dimensions/site-section.md) .
* Servrar: Använder [serverdimensionen](/help/components/dimensions/server.md) .
* Länkar: Innehåller rapporter som använder länkspårning.
   * Avsluta länkar: Använder [avslutningslänkdimensionen](/help/components/dimensions/exit-link.md) .
   * Filnedladdningar: Använder dimensionen [Hämta länk](/help/components/dimensions/download-link.md) .
   * Anpassade länkar: Använder dimensionen för [anpassad länk](/help/components/dimensions/custom-link.md) .
   * Sidorna hittades inte: Använder dimensionen [Sidor som inte hittades](/help/components/dimensions/pages-not-found.md) .

## Mobil

Innehåller rapporter om äldre mobilrapporter. Dessa rapporter baserar sina data på användaragentsträngen. De använder olika [mobildimensioner](/help/components/dimensions/mobile-dimensions.md) för sina respektive rapporter.

* Enheter: Använder dimensionen för [mobila enheter](/help/components/dimensions/mobile-dimensions.md) .
* Enhetstyp: Använder dimensionen för [mobilenhetstyp](/help/components/dimensions/mobile-dimensions.md) .
* Tillverkare: Använder dimensionen för [mobiltillverkare](/help/components/dimensions/mobile-dimensions.md) .
* Skärmstorlek: Använder dimensionen för [mobilskärmens storlek](/help/components/dimensions/mobile-dimensions.md) .
* Skärmhöjd: Använder höjddimensionen för [mobilskärmen](/help/components/dimensions/mobile-dimensions.md) .
* Skärmbredd: Använder dimensionen för [mobilskärmens bredd](/help/components/dimensions/mobile-dimensions.md) .
* Cookie-stöd: Använder dimensionen [Mobile cookie-stöd](/help/components/dimensions/mobile-dimensions.md) .
* Bildstöd: Använder dimensionen för stöd [för](/help/components/dimensions/mobile-dimensions.md) mobilbilder.
* Färgdjup: Använder dimensionen för [mobilt färgdjup](/help/components/dimensions/mobile-dimensions.md) .
* Stöd för ljud: Använder dimensionen [för stöd](/help/components/dimensions/mobile-dimensions.md) för mobilljud.
* Stöd för video: Använder dimensionen [Stöd](/help/components/dimensions/mobile-dimensions.md) för mobilvideo.
* Operativsystem (borttaget): Använder [mobiloperativsystemets (föråldrad)](/help/components/dimensions/mobile-dimensions.md) dimension.

## Banor

Innehåller rapporter som gör att du kan se sökdata för besökare.

* Nästa sidflöde: Använder en flödesrapport på dimensionsvärdet för den översta sidan. Banvyer liknar [instanser](/help/components/metrics/instances.md). Du kan ändra det rapporterade dimensionsvärdet. En liknande rapport i Analysis Workspace är tillgänglig med hjälp av en [Flow-visualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Nästa sida: Tar det översta siddimensionsvärdet och visar dig de nästa sidor besökarna besöker.
* Föregående sidflöde: Använder en flödesrapport på det översta siddimensionsvärdet En liknande rapport i Analysis Workspace är tillgänglig med hjälp av en [flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Föregående sida: Tar det översta siddimensionsvärdet och visar de föregående sidorna besökarna kom från.
* Utfall: Gör att du kan välja siddimensionsvärden i steg, och visar andelen personer som inte följde och följde den banan. En liknande rapport i Analysis Workspace är tillgänglig med hjälp av en [utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Fullständiga sökvägar: Visar enskilda sökvägar som dimensionsvärden. Pensionärer på analysarbetsytan; använd [Flow-visualisering](../analysis-workspace/visualizations/c-flow/flow.md) i stället.
* PathFinder: Innehåller flera typer av rapporter som gör att du kan analysera sökvägar (tas bort i Analysis Workspace).
* Banlängd: Använder dimensionen för [besöksdjup](/help/components/dimensions/visit-depth.md) .
* Sidanalys
   * Sidsammanfattning: Tar det översta siddimensionsvärdet och visar en trendvy. Visar även startpunkter, tidigare sidor, slutpunkter och nästa sidor för det övre siddimensionsvärdet.
   * Läs in igen: Använder [siddimensionen](/help/components/dimensions/page.md) med måttet [Läser in igen](/help/components/metrics/reloads.md) .
   * Tid som använts på sidan: Använder den [tid som har använts på sidan - paketerad](/help/components/dimensions/time-spent-on-page.md) dimension.
   * Klicka på sidan: Tar det översta siddimensionsvärdet och visar hur många klick det tog att gå till den sidan under ett visst besök.
* Poster och utträden
   * Anmälningssidor: Använder dimensionen för [anmälningssidor](/help/components/dimensions/entry-dimensions.md) .
   * Ursprungliga startsidor: Använder [startsidans ursprungliga](/help/components/dimensions/entry-dimensions.md) dimension.
   * Besök enstaka sidor: Använder dimensionen [Sida](/help/components/dimensions/page.md) med segmentet&quot;Enkelsidiga besök&quot; från Adobe.
   * Avsluta sidor: Använder dimensionen [Avsluta sidor](/help/components/dimensions/exit-dimensions.md) .

> [!NOTE] Andra rapporter kan visas i den här mappen. De är andra dimensioner, t.ex. props, där du har aktiverat [delning](../../admin/admin/c-traffic-variables/traffic-var.md) under rapportsvitens inställningar.

## Trafikkällor

Innehåller en rapport som ger en inblick i var besökarna kom från innan de kom till er webbplats. Rapporterna fungerar inte korrekt om du inte anger [interna URL-filter](../../admin/admin/internal-url-filter-admin.md) korrekt under inställningarna för rapportsviten.

* Sök nyckelord - alla: Använder nyckelordsdimensionen [Sök](/help/components/dimensions/search-keyword.md) .
* Söknyckelord - betalt: Använder nyckelordet [Sök - betald](/help/components/dimensions/search-keyword.md) dimension.
* Söknyckelord - naturliga: Använder nyckelordet [Sök - naturlig](/help/components/dimensions/search-keyword.md) dimension
* Sökmotorer - alla: Använder [sökmotordimensionen](/help/components/dimensions/search-engine.md) .
* Sökmotorer - betalda: Använder [sökmotorn - betald](/help/components/dimensions/search-engine.md) dimension.
* Sökmotorer - naturliga: Använder [sökmotorn - naturlig](/help/components/dimensions/search-engine.md) dimension.
* Alla söksidrankningar: Använder rangordningsdimensionen [Alla söksidor](/help/components/dimensions/all-search-page-rank.md) .
* Referensdomäner: Använder [referensdomänens](/help/components/dimensions/referring-domain.md) dimension
* Ursprungliga referensdomäner: Använder den [ursprungliga refererande domändimensionen](/help/components/dimensions/original-referring-domain.md)
* Referenter: Använder [referensdimensionen](/help/components/dimensions/referrer.md) .
* Refererartyper: Använder [referensdimension](/help/components/dimensions/referrer-type.md) .

## Kampanjer

Innehåller rapporter huvudsakligen kring [spårningskoddimensionen](/help/components/dimensions/tracking-code.md) .

* Kampanjkonverteringstratt: Rapporterar klickningar, [utcheckningar](/help/components/metrics/checkouts.md), [beställningar](/help/components/metrics/orders.md)och [intäkter](/help/components/metrics/revenue.md) i en trattrapport. Mätvärdet för klickfrekvens liknar [instansmåttet](/help/components/metrics/instances.md) i samband med dimensionen för [spårningskod](/help/components/dimensions/tracking-code.md) . En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Spårningskod: Använder [spårningskoddimensionen](/help/components/dimensions/tracking-code.md) .

## Produkter

Innehåller rapporter huvudsakligen kring [produktdimensionen](/help/components/dimensions/product.md) .

* Produktkonverteringstratt: Rapporterar [produktvyer](/help/components/metrics/product-views.md), [kundvagnstillägg](/help/components/metrics/cart-additions.md), [utcheckningar](/help/components/metrics/checkouts.md), [beställningar](/help/components/metrics/orders.md), [enheter](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) och¥Revenue som en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produkter: Använder dimensionen [Produkter](/help/components/dimensions/product.md) .
* Korsförsäljning: Visar produkter som vanligen säljs tillsammans (som har tagits bort i Analysis Workspace).
* Kategorier: Använder [kategoridimensionen](/help/components/dimensions/category.md) .

## Bevarande av besökare

Innehåller rapporter om besökare som återvänder till din webbplats.

* Returfrekvens: Använder [returfrekvensdimensionen](/help/components/dimensions/return-frequency.md) .
* Returbesök: Trends the [Visits](/help/components/metrics/visits.md) metric over time with the Adobe-provided &#39;Return visit&#39; segment applied.
* Besöksnummer: Använder dimensionen för [besöksnumret](/help/components/dimensions/visit-number.md) .
* Försäljningscykel: Mapp för inköpsrelaterade rapporter.
   * Kundlojalitet: Använder [kundlojalitetsdimensionen](/help/components/dimensions/customer-loyalty.md) .
   * Dagar före första köpet: Använder dimensionen [Dagar före första inköp](/help/components/dimensions/days-before-first-purchase.md) .
   * Dagar sedan senaste köp: Använder dimensionen [Dagar sedan senaste köp](/help/components/dimensions/days-since-last-purchase.md) .
   * Dagens unika kunder: Trender [Dagens unika besökare](/help/components/metrics/unique-visitors.md) över tid med segmentet&quot;köpare&quot; från Adobe tillagda.
   * Unika kunder varje vecka: Trends [Weekly unique visits](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided &#39;purchasing&#39; segment applied.
   * Månatliga unika kunder: Trender [Månadens unika besökare](/help/components/metrics/unique-visitors.md) över tid med segmentet&quot;köpare&quot; som tillhandahålls av Adobe.
   * Kunder som är unika varje kvartal: Trender som är unika [besökare](/help/components/metrics/unique-visitors.md) varje kvartal över tiden med segmentet&quot;köpare&quot; från Adobe tillagda. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Årliga unika kunder: Trends [Yearly unique visitations](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided &#39;purchasing&#39; segment applied.

## Besökarprofil

Innehåller rapporter om vem som besöker er webbplats.

* Geosegmentering: Rapporter om var i världen träffar din sajt kommer ifrån.
   * Länder: Använder dimensionen [Länder](/help/components/dimensions/countries.md) .
   * Region: Använder dimensionen [Områden](/help/components/dimensions/regions.md) .
   * Städer: Använder dimensionen [Städer](/help/components/dimensions/cities.md) .
   * USA: Använder dimensionen för [USA](/help/components/dimensions/us-states.md) .
   * US DMA: Använder DMA-dimensionen i [USA](/help/components/dimensions/us-dma.md) .
* Språk: Använder dimensionen [Språk](/help/components/dimensions/language.md) .
* Tidszoner: Använder tidszonsdimensionen (indragen i Analysis Workspace). Dimensionsvärden är GMT-förskjutningen för träffen.
* Domän: Använder [domändimensionen](/help/components/dimensions/domain.md) .
* Domän på översta nivån: Använder domändimensionen på den översta nivån (pensionerad i Analysis Workspace). Den grupperar [domändimensionen](/help/components/dimensions/domain.md) i kategorier på högre nivå, vanligtvis efter domänens land.
* Teknik: Mappen innehåller rapporter om vad besökaren använde för att få åtkomst till din plats.
   * Webbläsare: Använder dimensionen [Webbläsare](/help/components/dimensions/browser.md) .
   * Typ av webbläsare: Använder dimensionen [Webbläsartyp](/help/components/dimensions/browser-type.md) .
   * Bredd på webbläsare: Använder [webbläsarbredden - bucketterad](/help/components/dimensions/browser-width.md) dimension.
   * Webbläsarhöjd: Använder [webbläsarhöjden - bucketed](/help/components/dimensions/browser-height.md) -dimensionen.
   * Operativsystem: Använder dimensionen för [operativsystem](/help/components/dimensions/operating-systems.md) .
   * Typ av operativsystem: Använder dimensionen för [operativsystemstyper](/help/components/dimensions/operating-system-types.md) .
   * Skärmfärgdjup: Använder [färgdjupsdimensionen](/help/components/dimensions/color-depth.md) .
   * Bildskärmsupplösning: Använder dimensionen [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md) .
   * Java: Använder den [Java-aktiverade](/help/components/dimensions/java-enabled.md) dimensionen.
   * JavaScript: Använder den JavaScript-aktiverade dimensionen (tas bort i Analysis Workspace). Dimensionsvärdena är &#39;Enabled&#39;, &#39;Disabled&#39; eller &#39;Unknown&#39;, beroende på om JavaScript är aktiverat i webbläsaren.
   * JavaScript-version: använder JavaScript-versionsdimensionen (tas bort i Analysis Workspace). Dimensionsvärden visar vilken version av JavaScript som webbläsaren använder.
   * Cookies: Använder [Cookie-supportdimensionen](/help/components/dimensions/cookie-support.md) .
   * Anslutningstyper: Använder dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md) .
   * Mobiloperatör: Använder dimensionen [Mobiloperatör](/help/components/dimensions/mobile-dimensions.md) .
* Besökarstatus: Använder lägesdimensionen (som tagits bort i Analysis Workspace). Dimensionsvärden härstammar från [`state`](../../implement/vars/page-vars/state.md) variabeln.
* Besökarens postnummer: Använder dimensionen för [postnummer](/help/components/dimensions/zip-code.md) .

## Anpassad konvertering

Innehåller rapporter som är specifika för implementeringen. Anpassade konverteringsrapporter använder [eVars](/help/components/dimensions/evar.md) som dimension.

## Anpassad trafik

Innehåller rapporter som är specifika för implementeringen. Anpassade trafikrapporter använder [props](/help/components/dimensions/prop.md) som dimension.

## Marknadsföringskanaler

Innehåller rapporter som omfattar [marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Översiktsrapport för kanal: En anpassad rapport som är specifik för Rapporter och analyser. Marknadsföringskanaler används som dimensionsvärden, med mätvärden som använder första eller sista beröringsattribuering.
* Första beröringskanalen: Använder dimensionen för den [första beröringskanalen](/help/components/dimensions/first-touch-channel.md) .
* Första beröringskanaldetalj: Använder detaljdimensionen för den [första beröringskanalen](/help/components/dimensions/first-touch-detail.md) .
* Senaste pekkanal: Använder dimensionen för den [sista beröringskanalen](/help/components/dimensions/last-touch-channel.md) .
* Senaste beröringskanalinformation: Använder dimensionen [Senaste beröringskanaldetalj](/help/components/dimensions/last-touch-detail.md) .

## Bokmärken

Innehåller rapporter som du har bokmärkt. Mer information finns i [Bokmärken](bookmarks.md) .

## Kontrollpaneler

Innehåller paneler som du har skapat. Mer information finns i [Kontrollpaneler](dashboard.md) .

## Mål

Innehåller mål som du har skapat. Mer information finns i [Målgrupper](targets.md) .

> [!NOTE] Om du inte hittar rapporten på den här hjälpsidan kan det bero på att administratören har ändrat namn på eller ändrat mappar. Se [Menyanpassning](/help/admin/admin/customize-menus.md) i användarhandboken för Admin.
