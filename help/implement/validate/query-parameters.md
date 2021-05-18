---
title: Frågeparametrar för datainsamling
description: Visar alla frågesträngsparametrar som används i bildbegäranden.
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
source-git-commit: 7025d132da9d281da6d57973a195a5e86a39bf18
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---

# Frågeparametrar för datainsamling

I följande tabell visas alla frågesträngsparametrar som Adobe använder i bildbegäranden. Den här informationen kan användas vid felsökning med [paketanalyserare](packet-monitor.md), när [maskinkodade bildbegäranden](../other/hardcoded.md) eller när du använder [dynamiska variabler](../vars/page-vars/dynamic-variables.md).

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
| `c1` - `c75` | [`prop1` -  `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md) eller anpassade trafikvariabler. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Den typ av valuta som används i träffen. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Antalet perioder i en domän. Används för att hjälpa till att lagra cookies korrekt. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Teckenkodningen för bildbegäran. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Besökarens kakas livstid. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Används i [platssektionerna](/help/components/dimensions/site-section.md)-dimensionen. |
| `cp` | Ingen | Används i dimensionen [Träfftyp](/help/components/dimensions/hit-type.md). |
| `ct` | Ingen | Används i dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Anger vad som ska användas för dynamiska variabler. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Kortskrift för frågesträngen `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Kommaavgränsad lista med händelser på sidan. Används av de flesta [mått](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Aktuell URL för sidan, upp till 255 byte. Används i dimensionen [sid-URL](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | URL-adresser som är längre än 255 byte delas. De första 255 byten visas i parametern `g` och alla återstående byte visas i parametern `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Kortskrift för frågesträngen `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Kortskrift för frågesträngen `pageType`. |
| `h1` -  `h5` | [`hier1` -  `hier5`](../vars/page-vars/hier.md) | Hierarkidimensioner. |
| `hp` | Ingen | Används inte längre. I tidigare versioner av Adobe Analytics fastställde du om den aktuella URL:en var webbläsarens hemsida. |
| `j` | Ingen | JavaScript-versionen som är installerad i webbläsaren. |
| `k` | Ingen | Används i [Cookie-stödet](/help/components/dimensions/cookie-support.md)-dimensionen. |
| `l1` -  `l3` | [`list1` -  `list3`](../vars/page-vars/list.md) | Listvariabler. |
| `lrt` | Ingen | Tidsåtgången för senaste begäran, som är tidsåtgången vid växling till och från den senaste begäran, i millisekunder. Det skickas bara när mer än en begäran går ut från en sida eller när sidan är ett ensidigt program (SPA). |
| `mid` | Ingen | Experience Cloud besökar-ID. |
| `ndh` | Ingen | En flagga som anger om bildbegäran härstammar från AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Hjälper till att avgöra var cookies är inställda. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Objektidentifierare för den sista sidan. Används i Activity Map. |
| `ot` | Ingen | Objektnamn för den sista sidan. Används i tidigare versioner av Activity Map. |
| `p` | Ingen | Används inte längre. Lista över plugin-program som används i webbläsaren. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Används i dimensionen [Sida](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Används i dimensionen [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Ingen | Endast inställd för nya besökare och alltid inställd på `true`. Förhindra oändliga omdirigeringar. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Anger typen av anpassad länk. Krävs för [anpassade länkar](/help/components/dimensions/custom-link.md), [Hämta länkar](/help/components/dimensions/download-link.md) och [Avsluta länkar](/help/components/dimensions/exit-link.md). |
| `pev1` | Ingen | Den URL som den anpassade länken inträffade på. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Eget länknamn. |
| `pev3` | Ingen | Används inte längre. Spårade milstolpar i tidigare versioner av videorapporter. |
| `pf` | Ingen | Plattformsflagga. endast för Adobe. Får ej ändras. |
| `pid` | Ingen | Sididentifierare för sista sidan. Används i tidigare versioner av Activity Map. |
| `pidt` | Ingen | Sididentifierartyp för sista sidan. Används i tidigare versioner av Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Kortskrift för frågesträngen `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabeln Produkter. Används i dimensionerna [Produkt](/help/components/dimensions/product.md) och [Kategori](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Används för att deduplicera inköp. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL för träffen. Används i trafikkällans dimensioner, till exempel [Referent](/help/components/dimensions/referrer.md) och [Refererande domän](/help/components/dimensions/referring-domain.md) |
| `s` | Ingen | Skärmupplösning, i `width x height`. Används i dimensionen [Bildskärmsupplösningar](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | [](/help/components/dimensions/server.md) Serverdimension. |
| `sv` | [`server`](../vars/page-vars/server.md) | Kortskrift för frågesträngen `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Tillståndsdimension. |
| `t` | Ingen | Datum/tid för träffen som genererats. Använder formatet `dd/mm/yyyy hh:mm:ss w o`.<br>-  `dd/mm/yyyy hh:mm:ss` är datum/tid i JavaScript. Månad `0` är januari, medan månad `11` är december.<br>-  `w` är veckodagen. `0` är söndag, medan  `6` är lördag.<br>-  `o` är den negativa GMT-förskjutningen i minuter. Till exempel är `420` GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Den anpassade tidsstämpeln med träffen. Används vanligtvis för spårning offline. |
| `v` | Ingen | Används i dimensionen [Java enabled](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Spårningskoddimension ](/help/components/dimensions/tracking-code.md) . |
| `v1` -  `v250` | [`evar1` -  `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md) eller anpassade konverteringsdimensioner. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabel för besökar-ID. |
| `vmk` | `vmk` | Används inte längre. Nyckel för migrering av besökare, som hjälper till att migrera implementeringar från tredjepartscookies till cookies från första part. |
| `vvp` | `variableProvider` | Används i dataanslutningar. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Används tillsammans med datakällor för att knyta samman online- och offlinedata. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Används i dimensionen [Postnummer](/help/components/dimensions/zip-code.md). |
