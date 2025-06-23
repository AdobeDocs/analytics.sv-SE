---
title: decodeLinkParameters
description: Aktivera eller inaktivera länkspårningsvariabler för AppMeasurement-dubbelkodning.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# decodeLinkParameters

Variabeln `decodeLinkParameters` är en boolesk variabel som avgör om länkspårningsvariabler kodas en gång (om den är `true`) eller två gånger (om den är `false`). Den påverkar bara `linkName` (del av metoden [`tl()`](../functions/tl-method.md)) och [`linkURL`](linkurl.md). AppMeasurement v2.24.0 eller senare krävs. Standardvärdet för variabeln är `false`.

I tidigare versioner av AppMeasurement än v2.24.0 var länkspårningsvariabler alltid URL-kodade två gånger. Även om det inte är något problem för implementeringar som vanligtvis kräver tecken med en byte, så har dubbelkodningen skapat felaktigt kodade värden för flerbytetecken i rapporter. Om variabeln anges till `true` kodas länkspårningsvärden en gång, vilket vanligtvis är det önskade beteendet.

* Om implementeringen använder flerbytetecken och länkspårningsvariabler är URL-avkodade för att förskjuta AppMeasurement dubbelkodning, anger du den här variabeln till `false`. Detta värde bevarar befintliga AppMeasurement-funktioner.
* Om flerbytetecken används i implementeringen och du inte anger länkspårningsvärden för URL-avkodning rekommenderar Adobe att variabeln ställs in på `true`.
* Om implementeringen inte använder flerbytetecken behövs inte den här variabeln. Adobe rekommenderar dock att variabeln ställs in på `true` om flerbytetecken skickas.

## Dubbelkoda länkparametrar med Web SDK

Den här variabeln är specifik för AppMeasurement och behövs inte i någon typ av Web SDK-implementering.

## Dubbelkoda länkparametrar med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurement-syntax.

## s.decodeLinkParameters i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.decodeLinkParameters` är en boolesk variabel som avgör om länkspårningsvärden kodas två gånger. Om variabeln inte definieras är standardvärdet `false` för att bevara funktionaliteten för befintliga implementeringar. Adobe rekommenderar att det här värdet anges till `true` för alla nya implementeringar, särskilt om URL-kodade värden visas i länkspårningsrapporter.

```js
s.decodeLinkParameters = true;
```
