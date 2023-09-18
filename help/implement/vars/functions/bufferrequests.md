---
title: bufferRequests
description: Förbättra tillförlitligheten när det gäller att samla in länkspårningsbegäranden för webbläsare som omedelbart tar bort sidan.
feature: Variables
source-git-commit: 58a82151a8cbc80318e4f4ab4186fcabef3f35ab
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# bufferRequests

The `bufferRequests()` kan du cachelagra bildbegäranden på den aktuella sidan i stället för att skicka dem till Adobe. Den här metoden är användbar i scenarier där en webbläsare inte stöder [`navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon) eller på annat sätt avbryter bildförfrågningar när en sida tas bort. Många versioner av WebKit-webbläsare, som Safari, uppvisar ofta beteendet att stoppa en bildbegäran när du klickar på en länk. The `bufferRequests()` finns för alla versioner av AppMeasurementet v2.25.0 eller senare.

När du ringer [`t()`](t-method.md) eller [`tl()`](tl-method.md) på en efterföljande sida i samma webbläsarsession och `bufferRequests()` ännu inte har anropats på den sidan, skickas alla buffrade begäranden utöver den sidans bildförfrågan. Buffertade begäranden skickas i rätt ordning, där den aktuella sidans bildbegäran skickas sist.

>[!TIP]
>
>Tidsstämpeln för buffrade begäranden delas med sidan som data skickas till. Om du vill ha mer precision i exakt den sekund en buffrad begäran spelas in, kan du ställa in [`timestamp`](../page-vars/timestamp.md) sidvariabel innan begäran buffras. Om du använder den här variabeln måste du se till att [Tidsstämplar (valfritt)](/help/technotes/timestamps-optional.md) är aktiverat - om det inte är det går alla tidsstämplade träffar förlorade permanent!

## Begränsningar

När du anropar `bufferRequests()` bör du tänka på följande begränsningar. Eftersom den här metoden använder [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), gäller många av dessa begränsningar:

* Mållänken måste finnas på samma domän och underdomän. Buffertade begäranden fungerar inte över domäner eller underdomäner, även om båda har samma Adobe Analytics-implementering. Den här begränsningen innebär också att du inte kan använda buffrade begäranden för att spåra slutlänkar.
* Mållänken måste använda samma protokoll som den aktuella sidan. Du kan inte skicka buffrade begäranden mellan HTTP och HTTPS.
* Buffrade begäranden lagras tills du ringer `t()` eller `tl()` utan att ringa `bufferRequests()` först, eller tills webbläsaren eller fliken stängs. Om en webbläsarsession avslutas innan du kan skicka data till Adobe går oskickade buffrade begäranden förlorade permanent.
* Om en webbläsare inte har stöd för [Webblagring-API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) eller [JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), skickas en varning till webbläsarkonsolen och AppMeasurementet försöker omedelbart skicka bildbegäran med `t()` -metod.

## Buffertade begäranden i Web SDK

Web SDK ger för närvarande inte möjlighet att buffra begäranden.

## Buffrade begäranden med Adobe Analytics-tillägget

Det finns inget dedikerat fält i Adobe Analytics-tillägget som kan använda den här variabeln. Använd den anpassade kodredigeraren enligt AppMeasurementen syntax.

## s.bufferRequests() i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Ring `bufferRequests()` metoden före anrop `t()` eller `tl()`. När `bufferRequests()` anropas skrivs efterföljande spårningsanrop till sessionslagringsplatsen i stället för att skickas till datainsamlingsservrar i Adobe.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
