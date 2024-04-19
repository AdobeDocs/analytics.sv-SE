---
title: Frågeparametrar för datainsamling
description: Visar alla frågesträngsparametrar som används i bildbegäranden.
feature: Validation
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 3%

---

# Frågeparametrar för datainsamling

I följande tabell visas alla frågesträngsparametrar som Adobe använder i bildbegäranden. Den här informationen kan användas vid felsökning med [Paketanalysatorer](packet-monitor.md), när [hårdkoda bildbegäranden](../other/hardcoded.md)eller när du använder [Dynamiska variabler](../vars/page-vars/dynamic-variables.md).

| Parameter | Analysimplementeringsvariabel | Beskrivning |
| --- | --- | --- |
| `aamlh` | Ingen | Platstips för Audience Manager. Används i Experience Cloud-integrering med delad profil. |
| `aamb` | Ingen | Audience Manager blob. Används i Experience Cloud-integrering med delad profil. |
| `aid` | Ingen | Besökar-ID för analys. |
| `AQB` | Ingen | Anger början på en frågesträng för bildbegäran. |
| `AQE` | Ingen | Anger slutet på en bildbegäran, vilket innebär att begäran inte trunkerades. |
| `bh` | Ingen | Webbläsarhöjd (i pixlar). Används i [Webbläsarhöjd](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | Ingen | Webbläsarbredd (i pixlar). Används i [Bredd på webbläsare](/help/components/dimensions/browser-width.md) dimension. |
| `c` | Ingen | Färgkvalitet (i bitar). Används i [Färgdjup](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Anger början på kontextdatavariabler. Innehåller aldrig ett värde. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Anger slutet på kontextdatavariabler. Innehåller aldrig ett värde. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md)eller anpassade trafikvariabler. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Den typ av valuta som används i träffen. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Antalet perioder i en domän. Används för att hjälpa till att lagra cookies korrekt. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Teckenkodningen för bildbegäran. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Besökarens kakas livstid. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Används i [Platsavsnitt](/help/components/dimensions/site-section.md) dimension. |
| `cp` | Ingen | Används i [Träfftyp](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | Ingen | Används i [Anslutningstyp](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Anger vad som ska användas för dynamiska variabler. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Shorthand for the `events` frågesträng. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Kommaavgränsad lista med händelser på sidan. Används av [mått](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Aktuell URL för sidan, upp till 255 byte. Används i [Sidans URL](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | URL-adresser som är längre än 255 byte delas. De första 255 byten visas i `g` och alla återstående byte visas i `-g` parameter. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Shorthand for the `pageName` frågesträng. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Shorthand for the `pageType` frågesträng. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefix för flera variabler som representerar [Klienttips](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Hierarkidimensioner. |
| `hp` | Ingen | Används inte längre. I tidigare versioner av Adobe Analytics fastställde du om den aktuella URL:en var webbläsarens hemsida. |
| `j` | Ingen | JavaScript-versionen som är installerad i webbläsaren. |
| `k` | Ingen | Används i [Cookie-stöd](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Listvariabler. |
| `lrt` | Ingen | Tidsåtgången för senaste begäran, som är tidsåtgången vid växling till och från den senaste begäran, i millisekunder. Det skickas bara när mer än en begäran går ut från en sida eller när sidan är ett ensidigt program (SPA). |
| `mid` | Ingen | Experience Cloud besökar-ID. |
| `ndh` | Ingen | En flagga som anger om bildbegäran kom från AppMeasurementet. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Hjälper till att avgöra var cookies är inställda. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Objekt-ID för den sista sidan. Används i Activity Map. |
| `ot` | Ingen | Objektnamn för den sista sidan. Används i tidigare versioner av Activity Map. |
| `p` | Ingen | Används inte längre. Lista över plugin-program som används i webbläsaren. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Används i [Sida](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Används i [Sidorna hittades inte](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | Ingen | Endast för nya besökare och alltid inställt på `true`. Förhindra oändliga omdirigeringar om en besökare avvisar cookies. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Anger typen av anpassad länk. Krävs för [Egna länkar](/help/components/dimensions/custom-link.md), [Hämta länkar](/help/components/dimensions/download-link.md)och [Avsluta länkar](/help/components/dimensions/exit-link.md). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | Den URL som den anpassade länken inträffade på. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Eget länknamn. |
| `pev3` | Ingen | Används inte längre. Spårade milstolpar i tidigare versioner av videorapporter. |
| `pf` | Ingen | Plattformsflagga, endast för Adobe. Får ej ändras. |
| `pid` | Ingen | Sid-ID för sista sidan. Används i tidigare versioner av Activity Map. |
| `pidt` | Ingen | Sididentifierartyp för sista sidan. Används i tidigare versioner av Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Shorthand for the `products` frågesträng. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabeln Produkter. Används i [Produkt](/help/components/dimensions/product.md) och [Kategori](/help/components/dimensions/category.md) dimensioner. |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Används för att deduplicera inköp. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL för träffen. Används i dimensionerna för trafikkällor, till exempel [Referent](/help/components/dimensions/referrer.md) och [Refererande domän](/help/components/dimensions/referring-domain.md) |
| `s` | Ingen | Skärmupplösning, i `width x height`. Används i [Övervaka upplösningar](/help/components/dimensions/monitor-resolution.md) dimension. |
| `server` | [`server`](../vars/page-vars/server.md) | [Server](/help/components/dimensions/server.md) dimension. |
| `sv` | [`server`](../vars/page-vars/server.md) | Shorthand for the `server` frågesträng. |
| `state` | [`state`](../vars/page-vars/state.md) | Tillståndsdimension. |
| `t` | Ingen | Datum/tid för träffen som genererats. Använder formatet `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` är datum/tid i JavaScript. Månad `0` är januari, under månad `11` är december.<br>- `w` är veckodagen. `0` är söndag, medan `6` är lördag.<br>- `o` är den negativa GMT-förskjutningen i minuter. Till exempel: `420` är GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Den anpassade tidsstämpeln med träffen. Används vanligtvis för spårning offline. |
| `v` | Ingen | Används i [Java aktiverat](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Spårningskod](/help/components/dimensions/tracking-code.md) dimension. |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md)eller anpassade konverteringsdimensioner. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabel för besökar-ID. |
| `vidn` | Ingen | Ange efter AppMeasurement för nya besökare. Innehåller ID-värdet som lagras i besökarens cookie. |
| `vmk` | `vmk` | Används inte längre. Nyckel för migrering av besökare, som hjälper till att migrera implementeringar från tredje part till cookies från första part. |
| `vvp` | `variableProvider` | Används i Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Används tillsammans med datakällor för att knyta samman online- och offlinedata. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Används i [Postnummer](/help/components/dimensions/zip-code.md) dimension. |
