---
title: tidsstämpel
description: Ange tidsstämpeln manuellt.
feature: Variables
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# tidsstämpel

The `timestamp` variabeln ställer in tidsstämpeln för träffen för tidsstämpelaktiverade rapportsviter manuellt.

>[!WARNING]
>
>Använd inte den här variabeln om rapportsviten inte uttryckligen har konfigurerats för att acceptera tidsstämplade träffar. AppMeasurementet ställer automatiskt in tiden för en träff för rapportsviter som inte stöder tidsstämplade träffar. Om du skickar en träff med den här variabeln till en rapportserie som inte stöder tidsstämplar, kommer dessa data att gå förlorade permanent.

## Tidsstämpla med Web SDK

Tidsstämpeln är [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/xdm-var-mapping.html) under XDM-fältet `xdm.timestamp`. Det här fältet har bara stöd för Unix-tid.

## Tidsstämpla med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.timestamp i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.timestamp` variabeln är en sträng som innehåller datum och tid för träffen. Giltiga tidsstämpelformat är [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) och [Unix-tid](https://en.wikipedia.org/wiki/Unix_time) på några sekunder.

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

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
* Timmar och minuter krävs. Sekunder är valfria men rekommenderas.
* Veckodatum och ordningstal stöds inte.
* Datumet kan vara i standardformat eller utökat format. Till exempel: `2024-01-01T00:00:00Z` och `20240101T000000Z` är båda giltiga.
* Andel minuter och sekunder är tekniskt giltiga, men bråktalen ignoreras av Adobe.
* Tidszoner stöds i standardformat och utökat format.

Följande är giltiga ISO 8601-värden i `timestamp` variabel:

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
