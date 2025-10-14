---
title: Frågeparametrar för datainsamling
description: Visar alla frågesträngsparametrar som används i bildbegäranden.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 3%

---

# Frågeparametrar för datainsamling

I följande tabell visas alla frågesträngsparametrar som Adobe använder i bildbegäranden. Den här informationen kan användas vid felsökning med [Packet analyzers](packet-monitor.md), när [hårdkodar en bild &#x200B;](../other/hardcoded.md) eller när [dynamiska variabler](../vars/page-vars/dynamic-variables.md) används.

| Parameter | Analysimplementeringsvariabel | Beskrivning |
| --- | --- | --- |
| `aamlh` | Ingen | Platstips för Audience Manager. Används i Experience Cloud-integrering med delad profil. |
| `aamb` | Ingen | Audience Manager blob. Används i Experience Cloud-integrering med delad profil. |
| `aid` | Ingen | Besökar-ID för analys. |
| `AQB` | Ingen | Anger början på en frågesträng för bildbegäran. |
| `AQE` | Ingen | Anger slutet på en bildbegäran, vilket innebär att begäran inte trunkerades. |
| `bh` | Ingen | Webbläsarhöjd (i pixlar). Används i dimensionen [Webbläsarhöjd](/help/components/dimensions/browser-height.md). |
| `bw` | Ingen | Webbläsarbredd (i pixlar). Används i dimensionen [Webbläsarbredd](/help/components/dimensions/browser-width.md). |
| `c` | Ingen | Färgkvalitet (i bitar). Används i dimensionen [Färgdjup](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Anger början på kontextdatavariabler. Innehåller aldrig ett värde. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Anger slutet på kontextdatavariabler. Innehåller aldrig ett värde. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) eller anpassade trafikvariabler. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Den typ av valuta som används i träffen. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Antalet perioder i en domän. Används för att hjälpa till att lagra cookies korrekt. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Teckenkodningen för bildbegäran. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Besökarens kakas livstid. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Används i dimensionen [Platsavsnitt](/help/components/dimensions/site-section.md). |
| `cp` | Ingen | Används i dimensionen [Träff](/help/components/dimensions/hit-type.md). |
| `ct` | Ingen | Används i dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Anger vad som ska användas för dynamiska variabler. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Kortskrift för frågesträngen `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Kommaavgränsad lista med händelser på sidan. Används av de flesta [mått](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Aktuell URL för sidan, upp till 255 byte. Används i dimensionen [Sida-URL](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | URL-adresser som är längre än 255 byte delas. De första 255 byten visas i parametern `g` och alla återstående byte visas i parametern `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Kortskrift för frågesträngen `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Kortskrift för frågesträngen `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefix för flera variabler som representerar [klienttips](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Hierarkidimensioner. |
| `hp` | Ingen | Används inte längre. I tidigare versioner av Adobe Analytics fastställde du om den aktuella URL:en var webbläsarens hemsida. |
| `j` | Ingen | Den version av JavaScript som är installerad i webbläsaren. |
| `k` | Ingen | Används i dimensionen för [cookie-stöd](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Listvariabler. |
| `lrt` | Ingen | Tidsåtgången för senaste begäran, som är tidsåtgången vid växling till och från den senaste begäran, i millisekunder. Det skickas endast när mer än en begäran går ut från en sida eller när sidan är ett SPA-program (single page application). |
| `mid` | Ingen | Experience Cloud besökar-ID. |
| `ndh` | Ingen | Flagga som anger om bildbegäran kommer från AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Hjälper till att avgöra var cookies är inställda. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Objekt-ID för den sista sidan. Används i Activity Map. |
| `ot` | Ingen | Objektnamn för den sista sidan. Används i tidigare versioner av Activity Map. |
| `p` | Ingen | Används inte längre. Lista över plugin-program som används i webbläsaren. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Används i dimensionen [Sida](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Används i dimensionen [Sidor som inte hittas](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Ingen | Endast inställd för nya besökare och alltid inställd på `true`. Förhindra oändliga omdirigeringar om en besökare avvisar cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Anger typen av anpassad länk. Krävs för [anpassade länkar](/help/components/dimensions/custom-link.md), [Hämta länkar](/help/components/dimensions/download-link.md) och [Avsluta länkar](/help/components/dimensions/exit-link.md). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | Den URL som den anpassade länken inträffade på. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Eget länknamn. |
| `pev3` | Ingen | Används inte längre. Spårade milstolpar i tidigare versioner av videorapporter. |
| `pf` | Ingen | Plattformsflagga; endast för Adobe. Får ej ändras. |
| `pid` | Ingen | Sid-ID för sista sidan. Används i tidigare versioner av Activity Map. |
| `pidt` | Ingen | Sididentifierartyp för sista sidan. Används i tidigare versioner av Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Kortskrift för frågesträngen `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabeln Produkter. Används i dimensionerna [Produkt](/help/components/dimensions/product.md) och [Kategori](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Används för att deduplicera inköp. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL för träffen. Används i trafikkällans dimensioner, till exempel [Referent](/help/components/dimensions/referrer.md) och [Referensdomän](/help/components/dimensions/referring-domain.md) |
| `s` | Ingen | Skärmupplösning, om `width x height`. Används i dimensionen [Bildskärmsupplösningar](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | Dimensionen [Server](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Kortskrift för frågesträngen `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Tillståndsdimension. |
| `t` | Ingen | Datum/tid för träffen som genererats. Använder formatet `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` är datum/tid i JavaScript. Månad `0` är januari medan månad `11` är december.<br>- `w` är veckodag. `0` är söndag, medan `6` är lördag.<br>- `o` är den negativa GMT-förskjutningen i minuter. `420` är till exempel GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Den anpassade tidsstämpeln med träffen. Används vanligtvis för spårning offline. |
| `v` | Ingen | Används i dimensionen [Java aktiverat](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Spårningskod](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) eller anpassade konverteringsdimensioner. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabel för besökar-ID. |
| `vidn` | Ingen | Anges av AppMeasurement för nya besökare. Innehåller ID-värdet som lagras i besökarens cookie. |
| `vmk` | `vmk` | Används inte längre. Nyckel för migrering av besökare, som hjälper till att migrera implementeringar från tredje part till cookies från första part. |
| `vvp` | `variableProvider` | Används i Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Används tillsammans med datakällor för att knyta samman online- och offlinedata. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Används i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). |
