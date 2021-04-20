---
title: Rapporter
description: Dimensionerna och måtten som Rapporter och analyser använder för varje rapport.
feature: Reports & Analytics Basics & Analytics Basics
role: Business Practitioner, Administrator
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 0%

---

# Rapporter

Varje rapport i Rapporter och analyser använder en dedikerad dimension och standardmått. Du kan ändra måtten i varje rapport och lägga till uppdelningar om du vill. I följande listor visas vilken dimension som används i varje rapport.

>[!NOTE]
>
>Din rapportmeny kan se annorlunda ut beroende på vilka anpassningar en administratör i organisationen har gjort. Se [Menyanpassning](/help/admin/admin/customize-menus.md) i användarhandboken för Admin.

## Mätvärden för webbplats

Innehåller rapporter som vanligtvis trendar med ett datumintervall. Innehåller också unika rapporter, till exempel rekommenderade rapporter och realtidsrapporter.

* Mina rekommenderade rapporter: Skapar en kontrollpanel som innehåller flera rapporter för omedelbar information.
* Nyckeltal: En rapport som gör det möjligt att trender upp till fem mätvärden i taget. Trender [Sidvyer](/help/components/metrics/page-views.md), [Besök](/help/components/metrics/visits.md) och [Unika besökare](/help/components/metrics/unique-visitors.md) som standard.
* Sidvyer: Trends the [Page views](/help/components/metrics/page-views.md) metric over time.
* Besök: Trends the [Visits](/help/components/metrics/visits.md) metric over time.
* Besökare: Trendar olika [unika besökare](/help/components/metrics/unique-visitors.md)-mått över tid.
   * Unika besökare: Räknar endast besökare en gång för hela det valda datumintervallet.
   * unika besökare varje timme: Räknar besökare flera gånger om de besöker under olika timmar av det valda datumintervallet.
   * Dagliga unika besökare: Räknar besökare flera gånger om de besöker under olika dagar i det valda datumintervallet.
   * unika besökare varje vecka: Räknar besökare flera gånger om de besöker under olika veckor i det valda datumintervallet.
   * unika besökare varje månad: Räknar besökare flera gånger om de besöker under olika månader i det valda datumintervallet.
   * Kvartalsvisa unika besökare: Räknar besökare flera gånger om de besöker under olika kvartal av det valda datumintervallet. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Unika besökare varje år: Räknar besökare flera gånger om de besöker under olika kalenderår i det valda datumintervallet.
* Tid per besök: Använder dimensionen [Tid per besök - bucketed](/help/components/dimensions/time-spent-per-visit.md).
* Tid före händelse: Använder [Tid före händelse](/help/components/dimensions/time-prior-to-event.md)-dimension.
* Inköp: Innehåller rapporter om inköpsbaserade mätvärden.
   * Inköpskonverteringstratt: Rapportera om [besök](/help/components/metrics/visits.md), [kundvagnar](/help/components/metrics/carts.md), [beställningar](/help/components/metrics/orders.md), [intäkter](/help/components/metrics/revenue.md) och [enheter](/help/components/metrics/units.md) i en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Intäkter: Trends the metric [Revenue](/help/components/metrics/revenue.md) over time.
   * Beställningar: Trends the metric [Orders](/help/components/metrics/orders.md) over time.
   * Enheter: Trends the metric [Units](/help/components/metrics/units.md) over time.
* Kundvagn: Innehåller rapporter om kundvagnsstatistik.
   * Konverteringsfunktion för kundvagn: Rapporterar [förekomster](/help/components/metrics/instances.md), [Kort](/help/components/metrics/carts.md), [Utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md) och [Inkomster](/help/components/metrics/revenue.md) i en trattrapport.
   * Kartor: Trends the metric [Carts](/help/components/metrics/carts.md) over time.
   * Vyer: Trends the metric [Cart views](/help/components/metrics/cart-views.md) over time.
   * Kundvagnstillägg: Trends the metric [Cart additions](/help/components/metrics/cart-additions.md) over time.
   * Borttagning av kundvagn: Trends the metric [Cart removals](/help/components/metrics/cart-removals.md) over time.
   * Utcheckningar: Trends the metric [Checkouts](/help/components/metrics/checkouts.md) over time.
* Anpassade händelser: Innehåller alla rapporter om anpassade [händelser](/help/components/metrics/custom-events.md) som är specifika för implementeringen.
* Börjor: Visar robotrelaterade rapporter.
   * Börjor: Visar de botar som oftast finns på webbplatsen. Se [Punktregler](../../admin/admin/bot-removal/bot-rules.md) i användarhandboken för Admin.
   * Punktsidor: Visar de sidor som träffar mest.
* Realtid: Visar vissa mått och mätvärden inom några sekunder efter datainsamlingen. Mer information finns i [Realtidsrapporter](/help/components/c-real-time-reporting/realtime.md).

## Webbplatsinnehåll

Innehåller rapporter om dimensioner som vanligtvis visar webbplatsinnehåll. Du kan använda klassificeringar i vissa av dessa rapporter. Att använda klassificeringar innebär att en rapport blir en meny som innehåller källrapporten och klassificeringsrapporterna.

* Sidor: Använder dimensionen [Sida](/help/components/dimensions/page.md).
* Site section: Använder dimensionen [Plats](/help/components/dimensions/site-section.md).
* Servrar: Använder dimensionen [Server](/help/components/dimensions/server.md).
* Länkar: Innehåller rapporter som använder länkspårning.
   * Avsluta länkar: Använder dimensionen [Avsluta länk](/help/components/dimensions/exit-link.md).
   * Filnedladdningar: Använder dimensionen [Hämta länk](/help/components/dimensions/download-link.md).
   * Anpassade länkar: Använder dimensionen [Anpassad länk](/help/components/dimensions/custom-link.md).
   * Sidorna hittades inte: Använder dimensionen [Sidor som inte hittas](/help/components/dimensions/pages-not-found.md).

## Mobil

Innehåller rapporter om äldre mobilrapporter. Dessa rapporter baserar sina data på användaragentsträngen. De använder olika [mobildimensioner](/help/components/dimensions/mobile-dimensions.md) för sina respektive rapporter.

* Enheter: Använder dimensionen [Mobil enhet](/help/components/dimensions/mobile-dimensions.md).
* Enhetstyp: Använder dimensionen [Mobile device type](/help/components/dimensions/mobile-dimensions.md).
* Tillverkare: Använder dimensionen [Mobile manufacturer](/help/components/dimensions/mobile-dimensions.md).
* Skärmstorlek: Använder dimensionen [Mobilskärm](/help/components/dimensions/mobile-dimensions.md).
* Skärmhöjd: Använder dimensionen [Höjd för mobilskärm](/help/components/dimensions/mobile-dimensions.md).
* Skärmbredd: Använder dimensionen [Bredd på mobil skärm](/help/components/dimensions/mobile-dimensions.md).
* Cookie-stöd: Använder dimensionen [Mobile cookie support](/help/components/dimensions/mobile-dimensions.md).
* Bildstöd: Använder dimensionen [Stöd för mobilbilder](/help/components/dimensions/mobile-dimensions.md).
* Färgdjup: Använder dimensionen [Mobil färgdjup](/help/components/dimensions/mobile-dimensions.md).
* Stöd för ljud: Använder dimensionen [Stöd för mobilt ljud](/help/components/dimensions/mobile-dimensions.md).
* Stöd för video: Använder dimensionen [Stöd för mobilvideo](/help/components/dimensions/mobile-dimensions.md).
* Operativsystem (borttaget): Använder dimensionen [Mobilt operativsystem (utgått)](/help/components/dimensions/mobile-dimensions.md).

## Sökvägar

Innehåller rapporter som gör att du kan se sökdata för besökare.

* Nästa sidflöde: Använder en flödesrapport på dimensionsobjektet för den översta sidan. Vyerna för sökvägar liknar [förekomster](/help/components/metrics/instances.md). Du kan ändra den rapporterade dimensionsobjektet. En liknande rapport i Analysis Workspace är tillgänglig med en [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Nästa sida: Tar det översta sidobjektet och visar dig de nästa sidor besökarna besöker.
* Föregående sidflöde: Använder en flödesrapport på dimensionsobjektet för den översta sidan En liknande rapport i Analysis Workspace är tillgänglig med en [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Föregående sida: Tar det översta sidobjektet och visar de föregående sidorna besökarna kom från.
* Utfall: Gör att du kan välja siddimensionsobjekt i steg, och visar andelen personer som inte följde den banan. En liknande rapport i Analysis Workspace är tillgänglig med en [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Fullständiga sökvägar: Visar enskilda sökvägar som dimensionsobjekt. Pensionärer i Analysis Workspace; använd [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md) i stället.
* PathFinder: Innehåller flera typer av rapporter som gör att du kan analysera banor (som tagits bort i Analysis Workspace).
* Banlängd: Använder dimensionen [Besöksdjup](/help/components/dimensions/visit-depth.md).
* Sidanalys
   * Sidsammanfattning: Tar det översta sidobjektet och visar en trendvy. Visar även startpunkter, tidigare sidor, slutpunkter och nästa sidor för den översta sidobjektet.
   * Läs in igen: Använder dimensionen [Sida](/help/components/dimensions/page.md) med måttet [Läser in](/help/components/metrics/reloads.md) igen.
   * Tid som använts på sidan: Använder den [tid som har använts på sidan - bucketterad](/help/components/dimensions/time-spent-on-page.md)-dimension.
   * Klicka på sidan: Tar den översta sidobjektet och visar antalet klick som det tog att gå till den sidan vid ett visst besök.
* Poster och utträden
   * Anmälningssidor: Använder dimensionen [Startsidor](/help/components/dimensions/entry-dimensions.md).
   * Ursprungliga startsidor: Använder den ursprungliga [dimensionen på startsidan](/help/components/dimensions/entry-dimensions.md).
   * Besök enstaka sidor: Använder dimensionen [Sida](/help/components/dimensions/page.md) med segmentet Enkelsidiga besök från Adobe.
   * Avsluta sidor: Använder dimensionen [Avsluta sidor](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>Andra rapporter kan visas i den här mappen. De är andra dimensioner, t.ex. props, där du har [målning aktiverad](../../admin/admin/c-traffic-variables/traffic-var.md) under rapportsvitens inställningar.

## Trafikkällor

Innehåller en rapport som ger en inblick i var besökarna kom från innan de kom till er webbplats. Rapporterna fungerar inte korrekt om du inte anger [interna URL-filter](../../admin/admin/internal-url-filter-admin.md) korrekt under inställningarna för rapportsviten.

* Sök nyckelord - alla: Använder dimensionen [Sök nyckelord](/help/components/dimensions/search-keyword.md).
* Söknyckelord - betalt: Använder [söknyckelordet - betald](/help/components/dimensions/search-keyword.md)-dimension.
* Söknyckelord - naturliga: Använder [söknyckelordet naturlig](/help/components/dimensions/search-keyword.md)-dimension
* Sökmotorer - alla: Använder dimensionen [Sökmotor](/help/components/dimensions/search-engine.md).
* Sökmotorer - betalda: Använder [sökmotorn - betald](/help/components/dimensions/search-engine.md)-dimension.
* Sökmotorer - naturliga: Använder [sökmotorn - naturlig](/help/components/dimensions/search-engine.md)-dimension.
* Alla söksidrankningar: Använder dimensionen [Alla söksidor rankas](/help/components/dimensions/all-search-page-rank.md).
* Referensdomäner: Använder dimensionen [Referensdomän](/help/components/dimensions/referring-domain.md)
* Ursprungliga referensdomäner: Använder dimensionen [Ursprunglig hänvisande domän](/help/components/dimensions/original-referring-domain.md)
* Referenter: Använder dimensionen [Referent](/help/components/dimensions/referrer.md).
* Refererartyper: Använder dimensionen [Referenstyp](/help/components/dimensions/referrer-type.md).

## Kampanjer

Innehåller rapporter främst kring [spårningskoden](/help/components/dimensions/tracking-code.md)-dimensionen.

* Kampanjkonverteringstratt: Rapporterar klickningar, [utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md) och [Intäkter](/help/components/metrics/revenue.md) i en trattrapport. Omklickningsmåttet liknar [förekomsterna](/help/components/metrics/instances.md) i samband med [spårningskoden](/help/components/dimensions/tracking-code.md)-dimensionen. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Spårningskod: Använder dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md).

## Produkter

Innehåller rapporter främst runt dimensionen [Produkt](/help/components/dimensions/product.md).

* Produktkonverteringstratt: Rapporterar [produktvyer](/help/components/metrics/product-views.md), [kundvagnstillägg](/help/components/metrics/cart-additions.md), [Utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md), [Enheter](/help/components/metrics/units.md) och [Intäkter](/help/components/metrics/revenue.md) i en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produkter: Använder dimensionen [Produkter](/help/components/dimensions/product.md).
* Korsförsäljning: Visar de produkter som vanligen säljs tillsammans (tas bort i Analysis Workspace).
* Kategorier: Använder dimensionen [Kategori](/help/components/dimensions/category.md).

## Bevarande av besökare

Innehåller rapporter om besökare som återvänder till din webbplats.

* Returfrekvens: Använder dimensionen [Returfrekvens](/help/components/dimensions/return-frequency.md).
* Returbesök: Trends the [Visits](/help/components/metrics/visits.md) metric over time with the Adobe-provided &#39;Return visit&#39; segment applied.
* Besöksnummer: Använder dimensionen [Besöksnummer](/help/components/dimensions/visit-number.md).
* Försäljningscykel: Mapp för inköpsrelaterade rapporter.
   * Kundlojalitet: Använder dimensionen [Kundlojalitet](/help/components/dimensions/customer-loyalty.md).
   * Dagar före första köpet: Använder dimensionen [Dagar före första köp](/help/components/dimensions/days-before-first-purchase.md).
   * Dagar sedan senaste köp: Använder dimensionen [Dagar sedan senaste köp](/help/components/dimensions/days-since-last-purchase.md).
   * Dagens unika kunder: Trender [Dagliga unika besökare](/help/components/metrics/unique-visitors.md) över tiden med segmentet köpare som tillhandahålls av Adobe.
   * Unika kunder varje vecka: Trender [Veckovis unika besökare](/help/components/metrics/unique-visitors.md) över tiden med segmentet köpare som tillhandahålls av Adobe.
   * Månatliga unika kunder: Trender [Månadsunika besökare](/help/components/metrics/unique-visitors.md) över tiden med segmentet köpare som tillhandahålls av Adobe.
   * Kunder som är unika varje kvartal: Trender [Kvartalsvisa unika besökare](/help/components/metrics/unique-visitors.md) över tiden med segmentet köpare som tillhandahålls av Adobe. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Årliga unika kunder: Trender [Årets unika besökare](/help/components/metrics/unique-visitors.md) över tiden med segmentet köpare som tillhandahålls av Adobe.

## Besökarprofil

Innehåller rapporter om vem som besöker er webbplats.

* Geosegmentering: Rapporter om var i världen träffar din sajt kommer ifrån.
   * Länder: Använder dimensionen [Länder](/help/components/dimensions/countries.md).
   * Region: Använder dimensionen [Områden](/help/components/dimensions/regions.md).
   * Städer: Använder dimensionen [Städer](/help/components/dimensions/cities.md).
   * USA: Använder dimensionen [USA](/help/components/dimensions/us-states.md).
   * US DMA: Använder dimensionen [US DMA](/help/components/dimensions/us-dma.md).
* Språk: Använder dimensionen [Språk](/help/components/dimensions/language.md).
* Tidszoner: Använder tidszonsdimensionen (indragen i Analysis Workspace). Dimensioner är GMT-förskjutningen för träffen.
* Domän: Använder dimensionen [Domän](/help/components/dimensions/domain.md).
* Domän på översta nivån: Använder domändimensionen på den översta nivån (pensionerad i Analysis Workspace). Dimensionen [domäner](/help/components/dimensions/domain.md) grupperas i kategorier på högre nivå, vanligtvis efter domänens land.
* Teknik: Mappen innehåller rapporter om vad besökaren använde för att få åtkomst till din plats.
   * Webbläsare: Använder dimensionen [Webbläsare](/help/components/dimensions/browser.md).
   * Typ av webbläsare: Använder dimensionen [Webbläsartyp](/help/components/dimensions/browser-type.md).
   * Bredd på webbläsare: Använder dimensionen [Webbläsarbredd - bucketterad](/help/components/dimensions/browser-width.md).
   * Webbläsarhöjd: Använder dimensionen [Webbläsarhöjd - bucketed](/help/components/dimensions/browser-height.md).
   * Operativsystem: Använder dimensionen [Operativsystem](/help/components/dimensions/operating-systems.md).
   * Typ av operativsystem: Använder dimensionen [Operativsystem](/help/components/dimensions/operating-system-types.md).
   * Skärmfärgdjup: Använder dimensionen [Färgdjup](/help/components/dimensions/color-depth.md).
   * Bildskärmsupplösning: Använder dimensionen [Skärmupplösning](/help/components/dimensions/monitor-resolution.md).
   * Java: Använder dimensionen [Java enabled](/help/components/dimensions/java-enabled.md).
   * JavaScript: Använder den JavaScript-aktiverade dimensionen (som tagits bort i Analysis Workspace). Dimensionen är &#39;Enabled&#39;, &#39;Disabled&#39; eller &#39;Unknown&#39;, beroende på om JavaScript är aktiverat i webbläsaren.
   * JavaScript-version: använder JavaScript-versionsdimensionen (som tagits bort i Analysis Workspace). Dimensioner visar vilken version av JavaScript som används i webbläsaren.
   * Cookies: Använder dimensionen [Cookie-stöd](/help/components/dimensions/cookie-support.md).
   * Anslutningstyper: Använder dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md).
   * Mobiloperatör: Använder dimensionen [Mobiloperatör](/help/components/dimensions/mobile-dimensions.md).
* Besökarstatus: Använder dimensionen State (pensionerad i Analysis Workspace). Dimensionens objekt härstammar från variabeln [`state`](../../implement/vars/page-vars/state.md).
* Besökarens postnummer: Använder dimensionen [Postnummer](/help/components/dimensions/zip-code.md).

## Anpassad konvertering

Innehåller rapporter som är specifika för implementeringen. Anpassade konverteringsrapporter använder [eVars](/help/components/dimensions/evar.md) som dimension.

## Anpassad trafik

Innehåller rapporter som är specifika för implementeringen. Anpassade trafikrapporter använder [props](/help/components/dimensions/prop.md) som dimension.

## Marknadsföringskanaler

Innehåller rapporter som rör [Marknadskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Översiktsrapport för kanal: En anpassad rapport som är specifik för Rapporter och analyser. Marknadsföringskanaler används som dimensionsposter, med mätvärden som använder första eller sista beröringsattribuering.
* Första beröringskanalen: Använder dimensionen [Första beröringskanalen](/help/components/dimensions/first-touch-channel.md).
* Första beröringskanaldetalj: Använder dimensionen [Första beröringskanalen](/help/components/dimensions/first-touch-detail.md).
* Senaste pekkanal: Använder dimensionen [Senaste beröringskanal](/help/components/dimensions/last-touch-channel.md).
* Senaste beröringskanalinformation: Använder dimensionen [Senaste beröringskanal](/help/components/dimensions/last-touch-detail.md).

## Bokmärken

Innehåller rapporter som du har bokmärkt. Mer information finns i [Bokmärken](bookmarks.md).

## Kontrollpaneler

Innehåller paneler som du har skapat. Mer information finns i [Kontrollpaneler](dashboard.md).

## Målgrupper

Innehåller mål som du har skapat. Mer information finns i [Mål](targets.md).

>[!NOTE]
>
>Om du inte hittar rapporten på den här hjälpsidan kan det bero på att administratören har ändrat namn på eller ändrat mappar. Se [Menyanpassning](/help/admin/admin/customize-menus.md) i användarhandboken för Admin.
