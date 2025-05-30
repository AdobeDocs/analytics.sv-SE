---
title: Använda AppMeasurement med iframes
description: Få åtkomst till Adobe Analytics-variabler i en iframe eller en överordnad sida i en iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Använda AppMeasurement med iframes

Du kan referera till AppMeasurementen från både underordnade och överordnade iframes. Det är nödvändigt att definiera alla variabler på samma plats där AppMeasurementet finns. I följande exempel beskrivs hur du ställer in grundläggande AppMeasurement-variabler och -metoder i och utanför en iframe.

Om du använder taggar i Adobe Experience Platform måste du se till att spårningsobjektet är globalt tillgängligt. Se [Översikt över Adobe Analytics-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=sv-SE).

>[!CAUTION]
>
>Undvik att ta med AppMeasurementen bibliotek på både en överordnad sida och iframe. Om du gör det finns det risk att skicka flera bildbegäranden, få fler rapporter och fler fakturerbara serversamtal.

## Få åtkomst till AppMeasurement som finns i en iframe

Du kan komma åt AppMeasurementets variabler via iframe-objektet. I de här exemplen anges [pageName](../vars/page-vars/pagename.md) och metoden [t()](../vars/functions/t-method.md) anropas på två olika sätt för att referera till iframe-objektet.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Få åtkomst till AppMeasurementet inifrån en iframe

Du kan komma åt AppMeasurementets variabler på en överordnad sida inifrån en iframe. I det här exemplet ställs [pageName](../vars/page-vars/pagename.md) in och metoden [t()](../vars/functions/t-method.md) anropas med egenskapen [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

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

* Liksom med annan JavaScript-kod kan iframes bara kommunicera när domäner och protokoll matchar. De här exemplen fungerar inte om iframe-innehållet finns i en annan domän än det överordnade.
* Om AppMeasurementet finns i en iframe anges variabeln [`referrer`](../vars/page-vars/referrer.md) till den överordnade URL:en, inte till den faktiska refererande URL:en. Du kan ställa in variabeln `referrer` manuellt för att lösa problemet.
* [Adobe Experience Cloud-felsökaren](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=sv-SE) känner inte igen bildbegäranden som utlösts inom iframes.
* Activity Map visar inte heatmap-kartan över länkar som klickats i iframes. Hela iframe markeras i stället.
