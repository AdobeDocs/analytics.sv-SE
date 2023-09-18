---
title: decodeLinkParameters
description: Aktivera eller inaktivera länkspårningsvariabler för dubbelkodning av AppMeasurement.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# decodeLinkParameters

The `decodeLinkParameters` variabeln är en boolesk variabel som avgör om länkspårningsvariabler kodas en gång (om de anges till `true`) eller två gånger (om inställt på `false`). Det påverkar bara `linkName` (del av [`tl()`](../functions/tl-method.md) metod) och [`linkURL`](linkurl.md). AppMeasurementet v2.24.0 eller senare krävs för att kunna användas. Standardvärdet för variabeln är `false`.

I tidigare versioner av AppMeasurementet än v2.24.0 var länkspårningsvariabler alltid URL-kodade två gånger. Även om det inte är något problem för implementeringar som vanligtvis kräver tecken med en byte, så har dubbelkodningen skapat felaktigt kodade värden för flerbytetecken i rapporter. Anger variabeln till `true` kodar värden för länkspårning en gång, vilket vanligtvis är det önskade beteendet.

* Om implementeringen använder flerbytetecken och länkspårningsvariabler är URL-avkodade för att förskjuta AppMeasurementets dubbelkodning anger du den här variabeln till `false`. Detta värde bevarar AppMeasurementets befintliga funktioner.
* Om flerbytetecken används i implementeringen och du inte anger länkspårningsvärden för URL-avkodning rekommenderar Adobe att variabeln anges till `true`.
* Om implementeringen inte använder flerbytetecken behövs inte den här variabeln. Adobe rekommenderar dock att variabeln ställs in på `true` om flerbytetecken kan skickas.

## Dubbelkoda länkparametrar med Web SDK

Den här variabeln är specifik för AppMeasurement och behövs inte i någon typ av Web SDK-implementering.

## Dubbelkoda länkparametrar med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.decodeLinkParameters i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.decodeLinkParameters` variabeln är en boolesk variabel som avgör om länkspårningsvärden kodas två gånger. Om variabeln inte är definierad är standardvärdet `false` för att bevara funktionaliteten i befintliga implementeringar. Adobe rekommenderar att du anger det här värdet till `true` för alla nya implementeringar, särskilt om du ser URL-kodade värden i länkspårningsrapporter.

```js
s.decodeLinkParameters = true;
```
