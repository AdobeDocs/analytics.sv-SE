---
title: Rapporter
description: Dimensionerna och måtten som Rapporter och analyser använder för varje rapport.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
source-git-commit: 17b5185e5358d661157c20a2504cacdbd4a2cc3d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 0%

---

# Rapporter

{{ra-eol}}

Varje rapport i Rapporter och analyser använder en dedikerad dimension och standardmått. Du kan ändra måtten i varje rapport och lägga till uppdelningar om du vill. I följande listor visas vilken dimension som används i varje rapport.

>[!NOTE]
>
>Din rapportmeny kan se annorlunda ut beroende på vilka anpassningar en administratör i organisationen har gjort. Se [Anpassa menyer](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) i användarhandboken för Admin.

>[!IMPORTANT]
>Effektivt **31 december 2023** kommer Adobe att upphöra med rapporter och analyser och tillhörande rapporter och funktioner. Då slutar rapporter och analyser och alla rapporter och scheman att fungera. Rapporterna, visualiseringarna och den underliggande tekniken som används i Rapporter och analyser uppfyller inte längre Adobe teknikstandarder. De flesta funktionerna Rapporter och Analytics är tillgängliga i Analysis Workspace. Sedan Analysis Workspace lanserades 2015 har funktionerna och funktionerna i Rapporter och analyser flyttats till Analysis Workspace och en tröskel på arbetsflödets paritet har uppnåtts. Det här meddelandet förklarar hur utgånget är.

## Mätvärden för webbplats

Innehåller rapporter som vanligtvis trendar med ett datumintervall. Innehåller också unika rapporter, till exempel rekommenderade rapporter och realtidsrapporter.

* Mina rekommenderade rapporter: Skapar en kontrollpanel som innehåller flera rapporter för omedelbar information.
* Nyckeltal: En rapport som gör det möjligt att trender upp till fem mätvärden i taget. Trender [Sidvyer](/help/components/metrics/page-views.md), [Besök](/help/components/metrics/visits.md)och [Unika besökare](/help/components/metrics/unique-visitors.md) som standard.
* Sidvyer: Trender [Sidvyer](/help/components/metrics/page-views.md) mätvärden över tid.
* Besök: Trender [Besök](/help/components/metrics/visits.md) mätvärden över tid.
* Besökare: Olika trender [Unika besökare](/help/components/metrics/unique-visitors.md) mätvärden över tid.
   * Unika besökare: Räknar endast besökare en gång för hela det valda datumintervallet.
   * unika besökare varje timme: Räknar besökare flera gånger om de besöker under olika timmar av det valda datumintervallet.
   * Dagliga unika besökare: Räknar besökare flera gånger om de besöker under olika dagar i det valda datumintervallet.
   * unika besökare varje vecka: Räknar besökare flera gånger om de besöker under olika veckor i det valda datumintervallet.
   * unika besökare varje månad: Räknar besökare flera gånger om de besöker under olika månader i det valda datumintervallet.
   * Kvartalsvisa unika besökare: Räknar besökare flera gånger om de besöker under olika kvartal av det valda datumintervallet. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Unika besökare varje år: Räknar besökare flera gånger om de besöker under olika kalenderår i det valda datumintervallet.
* Tid per besök: Använder [Tid per besök - paketerad](/help/components/dimensions/time-spent-per-visit.md) dimension.
* Tid före händelse: Använder [Tid före händelse](/help/components/dimensions/time-prior-to-event.md) dimension.
* Inköp: Innehåller rapporter om inköpsbaserade mätvärden.
   * Inköpskonverteringstratt: Rapport om [Besök](/help/components/metrics/visits.md), [Korgar](/help/components/metrics/carts.md), [Beställningar](/help/components/metrics/orders.md), [Intäkter](/help/components/metrics/revenue.md)och [Enheter](/help/components/metrics/units.md) i en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Intäkter: Trends the metric [Intäkter](/help/components/metrics/revenue.md) över tid.
   * Beställningar: Trends the metric [Beställningar](/help/components/metrics/orders.md) över tid.
   * Enheter: Trends the metric [Enheter](/help/components/metrics/units.md) över tid.
* Kundvagn: Innehåller rapporter om kundvagnsstatistik.
   * Konverteringsfunktion för kundvagn: Rapporter [Instanser](/help/components/metrics/instances.md), [Korgar](/help/components/metrics/carts.md), [Utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md)och [Intäkter](/help/components/metrics/revenue.md) i en trattrapport.
   * Kartor: Trends the metric [Korgar](/help/components/metrics/carts.md) över tid.
   * Vyer: Trends the metric [Vyer](/help/components/metrics/cart-views.md) över tid.
   * Kundvagnstillägg: Trends the metric [Kundtillägg](/help/components/metrics/cart-additions.md) över tid.
   * Borttagning av kundvagn: Trends the metric [Borttagning av kundvagn](/help/components/metrics/cart-removals.md) över tid.
   * Utcheckningar: Trends the metric [Utcheckningar](/help/components/metrics/checkouts.md) över tid.
* Anpassade händelser: Innehåller alla rapporter runt anpassade rapporter [Händelser](/help/components/metrics/custom-events.md) specifikt för er implementering.
* Börjor: Visar robotrelaterade rapporter.
   * Börjor: Visar de botar som oftast finns på webbplatsen. Se [Punktregler](../../admin/admin/bot-removal/bot-rules.md) i användarhandboken för Admin.
   * Punktsidor: Visar de sidor som träffar mest.
* Realtid: Visar vissa mått och mätvärden inom några sekunder efter datainsamlingen. Se [Realtidsrapporter](/help/components/c-real-time-reporting/realtime.md) för mer information.

## Webbplatsinnehåll

Innehåller rapporter om dimensioner som vanligtvis visar webbplatsinnehåll. Du kan använda klassificeringar i vissa av dessa rapporter. Att använda klassificeringar innebär att en rapport blir en meny som innehåller källrapporten och klassificeringsrapporterna.

* Sidor: Använder [Sida](/help/components/dimensions/page.md) dimension.
* Site section: Använder [Site section](/help/components/dimensions/site-section.md) dimension.
* Servrar: Använder [Server](/help/components/dimensions/server.md) dimension.
* Länkar: Innehåller rapporter som använder länkspårning.
   * Avsluta länkar: Använder [Avsluta länk](/help/components/dimensions/exit-link.md) dimension.
   * Filnedladdningar: Använder [Hämta länk](/help/components/dimensions/download-link.md) dimension.
   * Anpassade länkar: Använder [Egen länk](/help/components/dimensions/custom-link.md) dimension.
   * Sidorna hittades inte: Använder [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md) dimension.

## Mobil

Innehåller rapporter om äldre mobilrapporter. Dessa rapporter baserar sina data på användaragentsträngen. De använder olika [mobildimensioner](/help/components/dimensions/mobile-dimensions.md) för sina respektive rapporter.

* Enheter: Använder [Mobil enhet](/help/components/dimensions/mobile-dimensions.md) dimension.
* Enhetstyp: Använder [Typ av mobil enhet](/help/components/dimensions/mobile-dimensions.md) dimension.
* Tillverkare: Använder [Mobil tillverkare](/help/components/dimensions/mobile-dimensions.md) dimension.
* Skärmstorlek: Använder [Skärmstorlek för mobiler](/help/components/dimensions/mobile-dimensions.md) dimension.
* Skärmhöjd: Använder [Höjd på mobilskärm](/help/components/dimensions/mobile-dimensions.md) dimension.
* Skärmbredd: Använder [Bredd på mobilskärm](/help/components/dimensions/mobile-dimensions.md) dimension.
* Cookie-stöd: Använder [Stöd för Mobile cookie](/help/components/dimensions/mobile-dimensions.md) dimension.
* Bildstöd: Använder [Stöd för mobilbilder](/help/components/dimensions/mobile-dimensions.md) dimension.
* Färgdjup: Använder [Mobil färgdjup](/help/components/dimensions/mobile-dimensions.md) dimension.
* Stöd för ljud: Använder [Stöd för mobilljud](/help/components/dimensions/mobile-dimensions.md) dimension.
* Stöd för video: Använder [Stöd för mobilvideo](/help/components/dimensions/mobile-dimensions.md) dimension.
* Operativsystem (borttaget): Använder [Mobiloperativsystem (borttaget)](/help/components/dimensions/mobile-dimensions.md) dimension.

## Sökvägar

Innehåller rapporter som gör att du kan se sökdata för besökare.

* Nästa sidflöde: Använder en flödesrapport på dimensionsobjektet för den översta sidan. Banvyer liknar [Instanser](/help/components/metrics/instances.md). Du kan ändra den rapporterade dimensionsobjektet. En liknande rapport i Analysis Workspace finns tillgänglig med en [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Nästa sida: Tar det översta sidobjektet och visar dig de nästa sidor besökarna besöker.
* Föregående sidflöde: Använder en flödesrapport på dimensionsartikeln för den översta sidan En liknande rapport i Analysis Workspace är tillgänglig med en [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md).
* Föregående sida: Tar det översta sidobjektet och visar de föregående sidorna besökarna kom från.
* Utfall: Gör att du kan välja siddimensionsobjekt i steg, och visar andelen personer som inte följde den banan. En liknande rapport i Analysis Workspace finns tillgänglig med en [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Fullständiga sökvägar: Visar enskilda sökvägar som dimensionsobjekt. Pensionärer i Analysis Workspace; använder [Flödesvisualisering](../analysis-workspace/visualizations/c-flow/flow.md) i stället.
* PathFinder: Innehåller flera typer av rapporter som gör att du kan analysera banor (som tagits bort i Analysis Workspace).
* Banlängd: Använder [Besöksdjup](/help/components/dimensions/visit-depth.md) dimension.
* Sidanalys
   * Sidsammanfattning: Tar det översta sidobjektet och visar en trendvy. Visar även startpunkter, tidigare sidor, slutpunkter och nästa sidor för den översta sidobjektet.
   * Läs in igen: Använder [Sida](/help/components/dimensions/page.md) dimension med [Läs in igen](/help/components/metrics/reloads.md) mätvärden.
   * Tid som använts på sidan: Använder [Tid som använts på sidan - blockerad](/help/components/dimensions/time-spent-on-page.md) dimension.
   * Klicka på sidan: Tar den översta sidobjektet och visar antalet klick som det tog att gå till den sidan vid ett visst besök.
* Poster och utträden
   * Anmälningssidor: Använder [Startsidor](/help/components/dimensions/entry-dimensions.md) dimension.
   * Ursprungliga startsidor: Använder [Startsida, original](/help/components/dimensions/entry-dimensions.md) dimension.
   * Besök enstaka sidor: Använder [Sida](/help/components/dimensions/page.md) dimensionen med segmentet&quot;Enkelsidiga besök&quot; som Adobe har angetts.
   * Avsluta sidor: Använder [Avsluta sidor](/help/components/dimensions/exit-dimensions.md) dimension.

>[!NOTE]
>
>Andra rapporter kan visas i den här mappen. De är andra dimensioner, till exempel proppar, där du har [målning aktiverad](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) under rapportsvitens inställningar.

## Trafikkällor

Innehåller en rapport som ger en inblick i var besökarna kom från innan de kom till er webbplats. Rapporterna fungerar inte korrekt om du inte anger rätt [Interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) under rapportsvitens inställningar.

* Sök nyckelord - alla: Använder [Söknyckelord](/help/components/dimensions/search-keyword.md) dimension.
* Söknyckelord - betalt: Använder [Söknyckelord - betalt](/help/components/dimensions/search-keyword.md) dimension.
* Söknyckelord - naturliga: Använder [Söknyckelord - naturligt](/help/components/dimensions/search-keyword.md) dimension
* Sökmotorer - alla: Använder [Sökmotor](/help/components/dimensions/search-engine.md) dimension.
* Sökmotorer - betalda: Använder [Sökmotor - betald](/help/components/dimensions/search-engine.md) dimension.
* Sökmotorer - naturliga: Använder [Sökmotor - naturlig](/help/components/dimensions/search-engine.md) dimension.
* Alla söksidrankningar: Använder [Alla söksidor rankade](/help/components/dimensions/all-search-page-rank.md) dimension.
* Referensdomäner: Använder [Refererande domän](/help/components/dimensions/referring-domain.md) dimension
* Ursprungliga referensdomäner: Använder [Ursprunglig hänvisande domän](/help/components/dimensions/original-referring-domain.md) dimension
* Referenter: Använder [Referent](/help/components/dimensions/referrer.md) dimension.
* Refererartyper: Använder [Referenstyp](/help/components/dimensions/referrer-type.md) dimension.

## Kampanjer

Innehåller rapporter huvudsakligen runt [Spårningskod](/help/components/dimensions/tracking-code.md) dimension.

* Kampanjkonverteringstratt: Rapporterar klickningar, [Utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md)och [Intäkter](/help/components/metrics/revenue.md) i en trattrapport. Mätvärdet för klickfrekvens liknar det för [Instanser](/help/components/metrics/instances.md) mätvärden i samband med [Spårningskod](/help/components/dimensions/tracking-code.md) dimension. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Spårningskod: Använder [Spårningskod](/help/components/dimensions/tracking-code.md) dimension.

## Produkter

Innehåller rapporter huvudsakligen runt [Produkt](/help/components/dimensions/product.md) dimension.

* Produktkonverteringstratt: Rapporter [Produktvyer](/help/components/metrics/product-views.md), [Kundtillägg](/help/components/metrics/cart-additions.md), [Utcheckningar](/help/components/metrics/checkouts.md), [Beställningar](/help/components/metrics/orders.md), [Enheter](/help/components/metrics/units.md)och [Intäkter](/help/components/metrics/revenue.md) i en trattrapport. En liknande visualisering uppnås i Analysis Workspace med [Utfallsvisualisering](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produkter: Använder [Produkter](/help/components/dimensions/product.md) dimension.
* Korsförsäljning: Visar de produkter som vanligen säljs tillsammans (tas bort i Analysis Workspace).
* Kategorier: Använder [Kategori](/help/components/dimensions/category.md) dimension.

## Bevarande av besökare

Innehåller rapporter om besökare som återvänder till din webbplats.

* Returfrekvens: Använder [Returfrekvens](/help/components/dimensions/return-frequency.md) dimension.
* Returbesök: Trender [Besök](/help/components/metrics/visits.md) mätresultat över tiden med segmentet&quot;Returbesök&quot; som tillhandahålls av Adobe.
* Besöksnummer: Använder [Besöksnummer](/help/components/dimensions/visit-number.md) dimension.
* Försäljningscykel: Mapp för inköpsrelaterade rapporter.
   * Kundlojalitet: Använder [Kundlojalitet](/help/components/dimensions/customer-loyalty.md) dimension.
   * Dagar före första köpet: Använder [Dagar före första köpet](/help/components/dimensions/days-before-first-purchase.md) dimension.
   * Dagar sedan senaste köp: Använder [Dagar sedan senaste köp](/help/components/dimensions/days-since-last-purchase.md) dimension.
   * Dagens unika kunder: Trender [Unika besökare varje dag](/help/components/metrics/unique-visitors.md) med Adobe-segmentet&quot;köpare&quot;.
   * Unika kunder varje vecka: Trender [Unika besökare varje vecka](/help/components/metrics/unique-visitors.md) med Adobe-segmentet&quot;köpare&quot;.
   * Månatliga unika kunder: Trender [unika besökare varje månad](/help/components/metrics/unique-visitors.md) med Adobe-segmentet&quot;köpare&quot;.
   * Kunder som är unika varje kvartal: Trender [unika besökare varje kvartal](/help/components/metrics/unique-visitors.md) med Adobe-segmentet&quot;köpare&quot;. Kvartalen är januari-mars, april-juni, juli-september och oktober-december.
   * Årliga unika kunder: Trender [Unika besökare varje år](/help/components/metrics/unique-visitors.md) med Adobe-segmentet&quot;köpare&quot;.

## Besökarprofil

Innehåller rapporter om vem som besöker er webbplats.

* Geosegmentering: Rapporter om var i världen träffar din sajt kommer ifrån.
   * Länder: Använder [Länder](/help/components/dimensions/countries.md) dimension.
   * Region: Använder [Regioner](/help/components/dimensions/regions.md) dimension.
   * Städer: Använder [Städer](/help/components/dimensions/cities.md) dimension.
   * USA: Använder [USA](/help/components/dimensions/us-states.md) dimension.
   * US DMA: Använder [US DMA](/help/components/dimensions/us-dma.md) dimension.
* Språk: Använder [Språk](/help/components/dimensions/language.md) dimension.
* Tidszoner: Använder tidszonsdimensionen (indragen i Analysis Workspace). Dimensioner är GMT-förskjutningen för träffen.
* Domän: Använder [Domän](/help/components/dimensions/domain.md) dimension.
* Domän på översta nivån: Använder domändimensionen på den översta nivån (pensionerad i Analysis Workspace). Den grupperar [domäner](/help/components/dimensions/domain.md) till kategorier på högre nivå, vanligtvis efter land i domänen.
* Teknik: Mappen innehåller rapporter om vad besökaren använde för att få åtkomst till din plats.
   * Webbläsare: Använder [Webbläsare](/help/components/dimensions/browser.md) dimension.
   * Typ av webbläsare: Använder [Typ av webbläsare](/help/components/dimensions/browser-type.md) dimension.
   * Bredd på webbläsare: Använder [Webbläsarbredd - blockerad](/help/components/dimensions/browser-width.md) dimension.
   * Webbläsarhöjd: Använder [Webbläsarhöjd - blockerad](/help/components/dimensions/browser-height.md) dimension.
   * Operativsystem: Använder [Operativsystem](/help/components/dimensions/operating-systems.md) dimension.
   * Typ av operativsystem: Använder [Operativsystemstyper](/help/components/dimensions/operating-system-types.md) dimension.
   * Skärmfärgdjup: Använder [Färgdjup](/help/components/dimensions/color-depth.md) dimension.
   * Bildskärmsupplösning: Använder [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md) dimension.
   * Java: Använder [Java aktiverat](/help/components/dimensions/java-enabled.md) dimension.
   * JavaScript: Använder den JavaScript-aktiverade dimensionen (som tagits bort i Analysis Workspace). Dimensionen är &#39;Enabled&#39;, &#39;Disabled&#39; eller &#39;Unknown&#39;, beroende på om JavaScript är aktiverat i webbläsaren.
   * JavaScript-version: använder JavaScript-versionsdimensionen (som tagits bort i Analysis Workspace). Dimensioner visar vilken version av JavaScript som används i webbläsaren.
   * Cookies: Använder [Cookie-stöd](/help/components/dimensions/cookie-support.md) dimension.
   * Anslutningstyper: Använder [Anslutningstyp](/help/components/dimensions/connection-type.md) dimension.
   * Mobiloperatör: Använder [Mobiloperatör](/help/components/dimensions/mobile-dimensions.md) dimension.
* Besökarstatus: Använder dimensionen State (pensionerad i Analysis Workspace). Dimensionen kommer från [`state`](../../implement/vars/page-vars/state.md) variabel.
* Besökarens postnummer: Använder [Postnummer](/help/components/dimensions/zip-code.md) dimension.

## Anpassad konvertering

Innehåller rapporter som är specifika för implementeringen. Anpassade konverteringsrapporter använder [eVars](/help/components/dimensions/evar.md) som dimension.

## Anpassad trafik

Innehåller rapporter som är specifika för implementeringen. Användning av anpassade trafikrapporter [proppar](/help/components/dimensions/prop.md) som dimension.

## Marknadsföringskanaler

Innehåller rapporter som innehåller [Marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Översiktsrapport för kanal: En anpassad rapport som är specifik för Rapporter och analyser. Marknadsföringskanaler används som dimensionsposter, med mätvärden som använder första eller sista beröringsattribuering.
* Första beröringskanalen: Använder [Första beröringskanalen](/help/components/dimensions/first-touch-channel.md) dimension.
* Första beröringskanaldetalj: Använder [Första beröringskanaldetalj](/help/components/dimensions/first-touch-detail.md) dimension.
* Senaste pekkanal: Använder [Senaste pekkanal](/help/components/dimensions/last-touch-channel.md) dimension.
* Senaste beröringskanalinformation: Använder [Senaste beröringskanaldetalj](/help/components/dimensions/last-touch-detail.md) dimension.

## Bokmärken

Innehåller rapporter som du har bokmärkt. Se [Bokmärken](bookmarks.md) för mer information.

## Kontrollpaneler

Innehåller paneler som du har skapat. Se [Kontrollpaneler](dashboard.md) för mer information.

## Målgrupper

Innehåller mål som du har skapat. Se [Målgrupper](targets.md) för mer information.

>[!NOTE]
>
>Om du inte hittar rapporten på den här hjälpsidan kan det bero på att administratören har ändrat namn på eller ändrat mappar. Se [Anpassa menyer](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) i användarhandboken för Admin.
