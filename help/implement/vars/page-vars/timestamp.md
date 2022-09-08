---
title: tidsstämpel
description: Ange tidsstämpeln för träffen manuellt.
feature: Variables
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
source-git-commit: a41fed835b6dcd3979111a7b13eaf33b63a3b2ec
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# tidsstämpel

The `timestamp` variabeln ställer in tidsstämpeln för träffen för tidsstämpelaktiverade rapportsviter manuellt.

>[!WARNING]
>
>Använd inte den här variabeln om rapportsviten inte uttryckligen har konfigurerats för att acceptera tidsstämplade träffar. AppMeasurement ställer automatiskt in tiden för en träff för rapportsviter som inte stöder tidsstämplade träffar. Om du skickar en träff med den här variabeln till en rapportserie som inte stöder tidsstämplar, kommer dessa data att gå förlorade permanent.

## Tidsstämpla med Web SDK

Tidsstämpeln är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fältet `xdm.timestamp`. Det här fältet har bara stöd för Unix-tid.

## Tidsstämpla med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.timestamp i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

The `s.timestamp` variabeln är en sträng som innehåller datum och tid för träffen. Giltiga tidsstämpelformat är [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) och [Unix-tid](https://en.wikipedia.org/wiki/Unix_time).

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

Datum och tid uttryckt i [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) kan ta flera olika former. Adobe stöder inte alla funktioner i ISO 8601.

* Både datum och tid måste anges, åtskilda med `T`.
* Timmar och minuter krävs. sekunder är valfria men rekommenderas.
* Veckodatum och ordningstal stöds inte.
* Datumet kan vara i standardformat eller utökat format. Till exempel: `2020-01-01T00:00:00Z` och `20200101T000000Z` är båda giltiga.
* Andel minuter och sekunder är tekniskt giltiga, men bråktalen ignoreras av Adobe.
* Tidszoner stöds i standardformat och utökat format.

Följande är giltiga ISO 8601-värden i `timestamp` variabel:

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
