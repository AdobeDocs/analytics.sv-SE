---
title: decodeLinkParameters
description: Aktivera eller inaktivera länkspårningsvariabler för dubbelkodning av AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# decodeLinkParameters

Variabeln `decodeLinkParameters` är en boolesk variabel som avgör om länkspårningsvariabler kodas en gång (om den är `true`) eller två gånger (om den är `false`). Den påverkar bara `linkName` (del av metoden [`tl()`](../functions/tl-method.md)) och [`linkURL`](linkurl.md). AppMeasurementet v2.24.0 eller senare krävs för att kunna användas. Standardvärdet för variabeln är `false`.

I tidigare versioner av AppMeasurementet än v2.24.0 var länkspårningsvariabler alltid URL-kodade två gånger. Även om det inte är något problem för implementeringar som vanligtvis kräver tecken med en byte, så har dubbelkodningen skapat felaktigt kodade värden för flerbytetecken i rapporter. Om variabeln anges till `true` kodas länkspårningsvärden en gång, vilket vanligtvis är det önskade beteendet.

* Om implementeringen använder flerbytetecken och länkspårningsvariablerna är URL-avkodade för att förskjuta AppMeasurementets dubbelkodning anger du den här variabeln till `false`. Detta värde bevarar AppMeasurementets befintliga funktioner.
* Om flerbytetecken används i implementeringen och du inte anger länkspårningsvärden för URL-avkodning rekommenderar Adobe att variabeln ställs in på `true`.
* Om implementeringen inte använder flerbytetecken behövs inte den här variabeln. Adobe rekommenderar dock att variabeln ställs in på `true` om flerbytetecken skickas.

## Dubbelkoda länkparametrar med Web SDK

Den här variabeln är specifik för AppMeasurement och behövs inte i någon typ av Web SDK-implementering.

## Dubbelkoda länkparametrar med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.decodeLinkParameters i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.decodeLinkParameters` är en boolesk variabel som avgör om länkspårningsvärden kodas två gånger. Om variabeln inte definieras är standardvärdet `false` för att bevara funktionaliteten för befintliga implementeringar. Adobe rekommenderar att det här värdet anges till `true` för alla nya implementeringar, särskilt om URL-kodade värden visas i länkspårningsrapporter.

```js
s.decodeLinkParameters = true;
```
