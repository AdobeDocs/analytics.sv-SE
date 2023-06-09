---
title: doubleEncodeLinkParameters
description: Aktivera eller inaktivera länkspårningsvariabler för dubbelkodning av AppMeasurement.
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# doubleEncodeLinkParameters

The `doubleEncodeLinkParameters` variabeln är en boolesk variabel som avgör om länkspårningsvariabler kodas en gång (om de anges till `false`) eller två gånger (om inställt på `true`). Det påverkar bara `linkName` (del av [`tl()`](../functions/tl-method.md) metod) och [`linkURL`](linkurl.md). AppMeasurement 2.23.1 eller senare krävs. Standardvärdet för den här variabeln är `true`.

I tidigare versioner av AppMeasurementet var länkspårningsvariabler alltid URL-kodade två gånger. Även om det inte är något problem för implementeringar som vanligtvis kräver tecken med en byte, så har dubbelkodningen skapat felaktigt kodade värden för flerbytetecken i rapporter. Anger variabeln till `false` kodar värden för länkspårning en gång, vilket vanligtvis är det önskade beteendet.

* Om implementeringen använder flerbytetecken och länkspårningsvariabler är URL-avkodade för att förskjuta AppMeasurementets dubbelkodning anger du den här variabeln till `true`. Detta värde bevarar AppMeasurementets befintliga funktioner.
* Om flerbytetecken används i implementeringen och du inte anger länkspårningsvärden för URL-avkodning rekommenderar Adobe att variabeln anges till `false`.
* Om implementeringen inte använder flerbytetecken behövs inte den här variabeln. Adobe rekommenderar dock att variabeln ställs in på `false` om flerbytetecken kan skickas.

## Dubbelkoda länkparametrar med Web SDK

Den här variabeln är specifik för AppMeasurement och behövs inte i någon typ av Web SDK-implementering.

## Dubbelkoda länkparametrar med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.doubleEncodeLinkParameters i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

The `s.doubleEncodeLinkParameters` variabeln är en boolesk variabel som avgör om länkspårningsvärden kodas två gånger. Om variabeln inte är definierad är standardvärdet `true` för att bevara funktionaliteten i befintliga implementeringar. Adobe rekommenderar att du anger värdet till `false` för alla nya implementeringar, särskilt om du ser URL-kodade värden i länkspårningsrapporter.

```js
s.doubleEncodeLinkParameters = false;
```
