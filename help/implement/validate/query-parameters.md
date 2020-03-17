---
title: Frågeparametrar för datainsamling
description: Visar alla frågesträngsparametrar som används i bildbegäranden.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Frågeparametrar för datainsamling

I följande tabell visas alla frågesträngsparametrar som Adobe använder i bildbegäranden. Den här informationen kan användas vid felsökning med [paketanalyserare](packet-monitor.md), vid [hårdkodning av bildbegäranden](../other/hardcoded.md)eller när [dynamiska variabler](../vars/page-vars/dynamic-variables.md)används.

| Parameter | Analysimplementeringsvariabel | Beskrivning |
| --- | --- | --- |
| `aamlh` | Ingen | Platstips för Audience Manager. Används i Experience Cloud-integrering med delad profil. |
| `aamb` | Ingen | Audience Manager-blob. Används i Experience Cloud-integrering med delad profil. |
| `aid` | Ingen | Besökar-ID för analys. |
| `AQB` | Ingen | Anger början på en frågesträng för bildbegäran. |
| `AQE` | Ingen | Anger slutet på en bildbegäran, vilket innebär att begäran inte trunkerades. |
| `bh` | Ingen | Webbläsarhöjd (i pixlar). Används i höjddimensionen i webbläsaren. |
| `bw` | Ingen | Webbläsarbredd (i pixlar). Används i dimensionen Webbläsarbredd. |
| `c` | Ingen | Färgkvalitet (i bitar). Används i dimensionen Färgdjup. |
| `c.` | `contextData` | Anger början på kontextdatavariabler. Innehåller aldrig ett värde. |
| `.c` | `contextData` | Anger slutet på kontextdatavariabler. Innehåller aldrig ett värde. |
| `c1` - `c75` | `prop1` - `prop75` | Anpassade trafikvariabler. |
| `cc` | `currencyCode` | Den typ av valuta som används i träffen. |
| `cdp` | `cookieDomainPeriods` | Antalet perioder i en domän. Används för att hjälpa till att lagra cookies korrekt. |
| `ce` | `charSet` | Teckenkodningen för bildbegäran. |
| `cl` | `cookieLifetime` | Besökarens kakas livstid. |
| `ch` | `channel` | Används i dimensionen Platsavsnitt. |
| `cp` | Ingen | Används i dimensionen Träff. |
| `ct` | Ingen | Används i dimensionen Anslutningstyp. |
| `D` | `dynamicVariablePrefix` | Anger vad som ska användas för dynamiska variabler. |
| `ev` | `events` | Kortskrift för `events` frågesträngen. |
| `events` | `events` | Kommaavgränsad lista med händelser på sidan. |
| `g` | `pageURL` | Aktuell URL för sidan, upp till 255 byte. |
| `-g` | `pageURL` | URL-adresser som är längre än 255 byte delas. De första 255 byten visas i `g` parametern och alla återstående byte visas i `-g` parametern. |
| `gn` | `pageName` | Kortskrift för `pageName` frågesträngen. |
| `gt` | `pageType` | Kortskrift för `pageType` frågesträngen. |
| `h1` - `h5` | `hier1` - `hier5` | Hierarkivariabler. |
| `hp` | Ingen | Används inte längre. I tidigare versioner av Adobe Analytics fastställde du om den aktuella URL:en var webbläsarens hemsida. |
| `j` | Ingen | JavaScript-versionen som är installerad i webbläsaren. |
| `k` | Ingen | Används i Cookie-supportdimensionen. |
| `l1` - `l3` | `list1` - `list3` | Listvariabler. |
| `mid` | Ingen | Besökar-ID för Experience Cloud. |
| `ndh` | Ingen | En flagga som anger om bildbegäran härstammar från AppMeasurement. |
| `ns` | `visitorNameSpace` | Hjälper till att avgöra var cookies är inställda. |
| `oid` | `objectID` | Objektidentifierare för den sista sidan. Används i aktivitetskarta. |
| `ot` | Ingen | Objektnamn för den sista sidan. Används i tidigare versioner av aktivitetskartan. |
| `p` | Ingen | Används inte längre. Lista över plugin-program som används i webbläsaren. |
| `pageName` | `pageName` | Används i siddimensionen. |
| `pageType` | `pageType` | Används i dimensionen Hittade inte sidor. |
| `pccr` | Ingen | Endast för nya besökare och alltid inställt på `true`. Förhindrar oändliga omdirigeringar. |
| `pe` | `linkType` | Anger typen av anpassad länk. |
| `pev1` | Ingen | Den URL som den anpassade länken inträffade på. |
| `pev2` | Ingen | Eget länknamn. |
| `pev3` | Ingen | Används inte längre. Spårade milstolpar i tidigare versioner av videorapporter. |
| `pf` | Ingen | Plattformsflagga. endast för Adobe. Får ej ändras. |
| `pid` | Ingen | Sididentifierare för sista sidan. Används i tidigare versioner av aktivitetskartan. |
| `pidt` | Ingen | Sididentifierartyp för sista sidan. Används i tidigare versioner av aktivitetskartan. |
| `pl` | `products` | Kortskrift för `products` frågesträngen. |
| `products` | `products` | Variabeln Produkter. |
| `purchaseID` | `purchaseID` | Används för att deduplicera inköp. |
| `r` | `referrer` | URL för träffen. |
| `s` | Ingen | Används i dimensionen Bildskärmsupplösningar. Skärmupplösning, i `width x height`. |
| `server` | `server` | Serverdimension. |
| `sv` | `server` | Kortskrift för `server` frågesträngen. |
| `state` | `state` | Tillståndsdimension. |
| `t` | Ingen | Datum/tid för träffen som genererats. Använder formatet `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` är datum/tid i JavaScript. Månad `0` är januari, medan månad `11` är december.<br>- `w` är veckodagen. `0` är söndag, medan `6` är lördag.<br>- `o` är den negativa GMT-förskjutningen i minuter. Till exempel `420` är GMT-7. |
| `ts` | `timestamp` | Den anpassade tidsstämpeln med träffen. Används vanligtvis för spårning offline. |
| `v` | Ingen | Används i dimensionen Java Enabled. |
| `v0` | `campaign` | Spårningskod. |
| `v1` - `v250` | `evar1` - `eVar250` | Anpassade konverteringsdimensioner. |
| `vid` | `visitorID` | Variabel för besökar-ID. |
| `vmk` | `vmk` | Används inte längre. Hjälpte till att migrera från cookies från tredje part till cookies från första part. |
| `vvp` | `variableProvider` | Används i dataanslutningar. |
| `xact` | `transactionID` | Används med datakällor för att länka samman data. |
| `zip` | `zip` | Används i postnummer-dimensionen. |
