---
title: Frågeparametrar för datainsamling
description: Visar alla frågesträngsparametrar som används i bildbegäranden.
translation-type: tm+mt
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 5%

---


# Frågeparametrar för datainsamling

I följande tabell visas alla frågesträngsparametrar som Adobe använder i bildbegäranden. Den här informationen kan användas vid felsökning med [paketanalyserare](packet-monitor.md), vid [hårdkodning av bildbegäranden](../other/hardcoded.md)eller när [dynamiska variabler](../vars/page-vars/dynamic-variables.md)används.

| Parameter | Analytics-implementeringsvariabel | Beskrivning |
| --- | --- | --- |
| `aamlh` | Ingen | Platstips för Audience Manager. Används i Experience Cloud-integrering med delad profil. |
| `aamb` | Ingen | Audience Manager blob. Används i Experience Cloud-integrering med delad profil. |
| `aid` | Ingen | Analytics besökar-ID. |
| `AQB` | Ingen | Anger början på en frågesträng för bildbegäran. |
| `AQE` | Ingen | Anger slutet på en bildbegäran, vilket innebär att begäran inte trunkerades. |
| `bh` | Ingen | Webbläsarhöjd (i pixlar). Används i [webbläsarens höjddimension](/help/components/dimensions/browser-height.md) . |
| `bw` | Ingen | Webbläsarbredd (i pixlar). Används i dimensionen [Webbläsarbredd](/help/components/dimensions/browser-width.md) . |
| `c` | Ingen | Färgkvalitet (i bitar). Används i [färgdjupsdimensionen](/help/components/dimensions/color-depth.md) . |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Anger början på kontextdatavariabler. Innehåller aldrig ett värde. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Anger slutet på kontextdatavariabler. Innehåller aldrig ett värde. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Props](/help/components/dimensions/prop.md)eller anpassade trafikvariabler. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Den typ av valuta som används i träffen. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Antalet perioder i en domän. Används för att hjälpa till att lagra cookies korrekt. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Teckenkodningen för bildbegäran. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Besökarens kakas livstid. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Används i dimensionen för [platsavsnitt](/help/components/dimensions/site-section.md) . |
| `cp` | Ingen | Används i dimensionen [Träff](/help/components/dimensions/hit-type.md) . |
| `ct` | Ingen | Används i dimensionen [Anslutningstyp](/help/components/dimensions/connection-type.md) . |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Anger vad som ska användas för dynamiska variabler. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Kortskrift för `events` frågesträngen. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Kommaavgränsad lista med händelser på sidan. Används av de flesta [mätvärden](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | Aktuell URL för sidan, upp till 255 byte. Används i [sidans URL](/help/components/dimensions/page-url.md) -dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | URL-adresser som är längre än 255 byte delas. De första 255 byten visas i `g` parametern och alla återstående byte visas i `-g` parametern. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Kortskrift för `pageName` frågesträngen. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Kortskrift för `pageType` frågesträngen. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Hierarkidimensioner. |
| `hp` | Ingen | Används inte längre. I tidigare versioner av Adobe Analytics fastställde du om den aktuella URL:en var webbläsarens hemsida. |
| `j` | Ingen | JavaScript-versionen som är installerad i webbläsaren. |
| `k` | Ingen | Används i [Cookie-supportdimensionen](/help/components/dimensions/cookie-support.md) . |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Listvariabler. |
| `mid` | Ingen | Experience Cloud besökar-ID. |
| `ndh` | Ingen | En flagga som anger om bildbegäran härstammar från AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Hjälper till att avgöra var cookies är inställda. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Objektidentifierare för den sista sidan. Används i Activity Map. |
| `ot` | Ingen | Objektnamn för den sista sidan. Används i tidigare versioner av Activity Map. |
| `p` | Ingen | Används inte längre. Lista över plugin-program som används i webbläsaren. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Används i dimensionen [Sida](/help/components/dimensions/page.md) . |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Används i dimensionen [Sidor hittades](/help/components/dimensions/pages-not-found.md) inte. |
| `pccr` | Ingen | Endast för nya besökare och alltid inställt på `true`. Förhindra oändliga omdirigeringar. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Anger typen av anpassad länk. Krävs för [anpassade länkar](/help/components/dimensions/custom-link.md), [hämtningslänkar](/help/components/dimensions/download-link.md)och [avslutningslänkar](/help/components/dimensions/exit-link.md). |
| `pev1` | Ingen | Den URL som den anpassade länken inträffade på. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Eget länknamn. |
| `pev3` | Ingen | Används inte längre. Spårade milstolpar i tidigare versioner av videorapporter. |
| `pf` | Ingen | Platform-flagga, endast för Adobe. Får ej ändras. |
| `pid` | Ingen | Sididentifierare för sista sidan. Används i tidigare versioner av Activity Map. |
| `pidt` | Ingen | Sididentifierartyp för sista sidan. Används i tidigare versioner av Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Kortskrift för `products` frågesträngen. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabeln Produkter. Används i [produkt](/help/components/dimensions/product.md) - och [kategoridimensionerna](/help/components/dimensions/category.md) . |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Används för att deduplicera inköp. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL för träffen. Används i trafikkällans dimensioner, t.ex. [referensdomän](/help/components/dimensions/referrer.md) och [referensdomän](/help/components/dimensions/referring-domain.md) |
| `s` | Ingen | Skärmupplösning, i `width x height`. Används i dimensionen [Bildskärmsupplösningar](/help/components/dimensions/monitor-resolution.md) . |
| `server` | [`server`](../vars/page-vars/server.md) | [Serverdimension](/help/components/dimensions/server.md) . |
| `sv` | [`server`](../vars/page-vars/server.md) | Kortskrift för `server` frågesträngen. |
| `state` | [`state`](../vars/page-vars/state.md) | Tillståndsdimension. |
| `t` | Ingen | Datum/tid för träffen som genererats. Använder formatet `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` är datum/tid i JavaScript. Månad `0` är januari, medan månad `11` är december.<br>- `w` är veckodagen. `0` är söndag, medan `6` är lördag.<br>- `o` är den negativa GMT-förskjutningen i minuter. Till exempel `420` är GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Den anpassade tidsstämpeln med träffen. Används vanligtvis för spårning offline. |
| `v` | Ingen | Används i den [Java-aktiverade](/help/components/dimensions/java-enabled.md) dimensionen. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Spårningskod](/help/components/dimensions/tracking-code.md) . |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVars](/help/components/dimensions/evar.md)eller anpassade konverteringsdimensioner. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabel för besökar-ID. |
| `vmk` | `vmk` | Används inte längre. Nyckel för migrering av besökare, som hjälper till att migrera implementeringar från tredjepartscookies till cookies från första part. |
| `vvp` | `variableProvider` | Används i dataanslutningar. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Används tillsammans med datakällor för att knyta samman online- och offlinedata. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Används i dimensionen [Postnummer](/help/components/dimensions/zip-code.md) . |
