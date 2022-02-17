---
title: Använd AppMeasurement med iframes
description: Få åtkomst till Adobe Analytics-variabler i en iframe eller en överordnad sida i en iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Använd AppMeasurement med iframes

Du kan referera till AppMeasurement-variabler från både underordnade och överordnade iframes. Det är nödvändigt att definiera alla variabler på samma plats där AppMeasurement-biblioteket finns. I följande exempel beskrivs hur du ställer in grundläggande AppMeasurement-variabler och -metoder i och utanför en iframe.

Om du använder taggar i Adobe Experience Platform måste du se till att spårningsobjektet är globalt tillgängligt. Se [Översikt över Adobe Analytics-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

>[!CAUTION]
>
>Undvik att ta med AppMeasurement-bibliotek på både en överordnad sida och iframe. Om du gör det finns det risk att skicka flera bildbegäranden, få fler rapporter och fler fakturerbara serversamtal.

## Få åtkomst till AppMeasurement som finns i en iframe

Du kan komma åt AppMeasurement-variabler via iframe-objektet. De här exemplen har angetts [pageName](../vars/page-vars/pagename.md) och ringa [t(), metod](../vars/functions/t-method.md) använder du två olika sätt att referera till iframe-objektet.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Få åtkomst till AppMeasurement inifrån en iframe

Du kan komma åt AppMeasurement-variabler på en överordnad sida inifrån en iframe. Det här exemplet anger [pageName](../vars/page-vars/pagename.md) och anropar [t(), metod](../vars/functions/t-method.md) med [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) -egenskap.

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Använd `postMessage` och händelseavlyssnare

Du kan också använda `postMessage` och händelseavlyssnare för att ange variabler. Den här metoden kräver ingen direkt referens till en iframe.

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Begränsningar

* Precis som med annan JavaScript-kod kan iframes bara kommunicera när domäner och protokoll matchar. De här exemplen fungerar inte om iframe-innehållet finns i en annan domän än det överordnade.
* Om AppMeasurement finns i en iframe visas [`referrer`](../vars/page-vars/referrer.md) variabeln ställs in på den överordnade URL:en, inte den faktiska refererande URL:en. Du kan ställa in `referrer` variabel som löser problemet.
* The [Adobe Experience Cloud debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) känner inte igen bildbegäranden som utlöses inom iframes.
* Activity Map visar inte heatmap-kartan över länkar som klickats i iframes. Hela iframe markeras i stället.
