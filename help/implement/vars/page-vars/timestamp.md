---
title: tidsstämpel
description: Ange tidsstämpeln för träffen manuellt.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# tidsstämpel

Variabeln anger `timestamp` manuellt tidsstämpeln för träffen för tidsstämpelaktiverade rapportsviter.

> [!WARNING] Använd inte den här variabeln om rapportsviten inte uttryckligen har konfigurerats för att acceptera tidsstämplade träffar. AppMeasurement ställer automatiskt in tiden för en träff för rapportsviter som inte stöder tidsstämplade träffar. Om du skickar en träff med den här variabeln till en rapportserie som inte stöder tidsstämplar, kommer dessa data att gå förlorade permanent.

## Tidsstämpel i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.timestamp i AppMeasurement and Launch custom code editor

Variabeln `s.timestamp` är en sträng som innehåller datum och tid för träffen. Giltiga tidsstämpelformat är [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) och [Unix-tid](https://en.wikipedia.org/wiki/Unix_time).

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601-värden

Datum och tider som uttrycks i [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) kan ha flera olika former. Adobe stöder inte alla funktioner i ISO 8601.

* Både datum och tid måste anges, åtskilda med `T`.
* Timmar och minuter krävs. sekunder är valfria men rekommenderas.
* Veckodatum och ordningstal stöds inte.
* Datumet kan vara i standardformat eller utökat format. Till exempel `2020-01-01T00:00:00Z` och `20200101T000000Z` är båda giltiga.
* Minuter och sekunder i bråkdelar är tekniskt giltiga, men bråktalen ignoreras av Adobe.
* Tidszoner stöds i standardformat och utökat format.

Följande är giltiga ISO 8601-värden i `timestamp` variabeln:

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
