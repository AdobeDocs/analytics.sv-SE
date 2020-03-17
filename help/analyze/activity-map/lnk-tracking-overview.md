---
description: 'Activity Map spårar länkar med en mer robust algoritm som '
title: Robust länkspårning
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Robust länkspårning

Activity Map spårar länkar med en mer robust algoritm som:

* Innehåller spårning av sidområden för att undvika att samma länk blandas ihop mellan olika enheter eftersom länken visas på olika ställen på sidan.
* Ser till att länken är unik, vilket innebär att distinkta länkar inte kan tas bort för en på grund av problem med LinkID eller olika webbläsare gör.

Mer information om länkspårning i aktivitetskartan finns [här](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Hur spårning av aktivitetskarta kan samla in PII-data {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] Genom att aktivera spårning av aktivitetskarta kan du samla in data om personligt identifierbar information (PII). Dessa data kan användas fristående eller tillsammans med annan information för att identifiera, kontakta eller hitta en person, eller för att identifiera en individ i sitt sammanhang.

Här är några kända fall där PII-data kan samlas in med hjälp av aktivitetskartspårning:

* `Mailto` länkar. En mailto-länk är en typ av HTML-länk som aktiverar standardklienten för e-post på datorn för att skicka ett e-postmeddelande.
* `User ID` länkar som kan visas i sidhuvudet/sidfoten på en webbplats när användaren har loggat in.
* För finansinstitut kan kontonumret visas som en länk. Om du klickar på den hämtas länktexten.
* Vårdwebbplatser kan också ha PII-data som visas som länkar. Om du klickar på de här länkarna samlas länktexten in, vilket innebär att PII-data samlas in.
