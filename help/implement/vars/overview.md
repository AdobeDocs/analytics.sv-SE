---
title: Variabler, funktioner, metoder och plugin-program - översikt
description: Lär dig vilka variabler du kan ta med i data som du skickar till Adobe för att förbättra rapporteringen.
keywords: appmeasurement,variabler,var,konfiguration,sida,implementering
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Variabler, funktioner, metoder och plugin-program - översikt

Analytics ger ett antal variabler för att samla in analysdata. Variablerna i det här avsnittet är uppdelade i flera avsnitt:

* **Sidvariabler** är värden som vanligtvis används direkt vid rapportering. Vanliga sidvariabler inkluderar `props`, `eVars`och `events`.
* **Konfigurationsvariabler** är inställningsvärden som gör att rätt data når Adobe. Vanliga config-variabler inkluderar `trackingServerSecure`, `charSet`och `linkTrackVars`. Konfigurationsvariabler fyller vanligtvis inte i dimensionsobjekt.
* **Funktioner och metoder** är koddelar som utför en viss uppgift när de refereras. Vanliga funktioner inkluderar `t()`, `tl()`och `clearVars()`.

## Variabler och implementeringsmetoder

Adobe erbjuder flera sätt att implementera Adobe Analytics. På varje sida finns ett avsnitt om hur du implementerar variabeln med Web SDK, med Adobe Analytics-tillägget och med AppMeasurementet för JavaScript.

Här är en video om hur du konfigurerar variabler i Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## Operationsordning

AppMeasurement-bibliotek som publiceras av Adobe Analytics följer en viss ordning när data skickas till Adobe. Om du utför dessa åtgärder i fel ordning kan data vara ofullständiga.

1. Om webbplatsen använder ett datalager måste du se till att alla tillämpliga variabler fylls i först. Du kan till exempel fylla i `adobeDataLayer.page.title` med sidrubriken. Se [Datalager](../prepare/data-layer.md) för mer information.
2. Använd datalagret för att fylla i Analytics-variabler. <br/>Om du använder taggar i Adobe Experience Platform kan du utföra den här uppgiften genom att använda dataelement däremellan. Dataelement fylls med värden från datalagret. Exempel på dataelement `Page Title` hämtar värdet från datalagervariabeln `adobeDataLayer.page.title`. <br/>Sedan kan du använda dataelementet för att fylla i Analytics-variabler. Till exempel `eVar4` hämtar värdet från dataelement `Page Title`. <br/>Mer information finns i [Dataelement](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html), [Mappa datalagerobjekt till dataelement](../launch/layer-to-elements.md)och [Mappa taggdataelement till analysvariabler](../launch/elements-to-variable.md)
3. Anropa till sist spårningsfunktionen. De flesta AppMeasurement använder `t()` -metod, men vissa av de mobila SDK:s använder `track()`. När spårningsfunktionen anropas skickas alla variabler som stöds i Analytics-objektet till Adobe i form av en bildbegäran.

## Ogiltiga tecken

Följande tecken och strängar tillåts aldrig i JavaScript-variabler.

* Tabb (`0x09`)
* Radbrytning (`0x0D`)
* Newline (`0x0A`)
* HTML-taggar (t.ex. `<b></b>` eller `&#153`)

Vissa variabler har ytterligare begränsningar eller syntaxkrav. Till exempel [`products`](page-vars/products.md) variabelreserverar semikolon och kommatecken för att avgränsa separata produkter och kategorier.
