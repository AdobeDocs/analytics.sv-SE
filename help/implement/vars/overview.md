---
title: Variabler, funktioner, metoder och plugin-program - översikt
description: Lär dig vilka variabler du kan inkludera i data som du skickar till Adobe för att förbättra rapporteringen.
keywords: appmeasurement,variabler,var,konfiguration,sida,implementering
feature: Appmeasurement Implementation
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Variabler, funktioner, metoder och plugin-program - översikt

Analytics ger ett antal variabler för att samla in analysdata. Variablerna i det här avsnittet är uppdelade i flera avsnitt:

* **Sidvariabler** är värden som vanligtvis används direkt i rapporter. Vanliga sidvariabler är `props`, `eVars` och `events`.
* **Konfigurationsvariabler** är inställningsvärden som hjälper till att se till att rätt data når Adobe. Vanliga config-variabler är `trackingServerSecure`, `charSet` och `linkTrackVars`. Konfigurationsvariabler fyller vanligtvis inte i dimensionsobjekt.
* **Funktioner och metoder** är kodbitar som utför en viss uppgift när de refereras. Vanliga funktioner är `t()`, `tl()` och `clearVars()`.

## Variabler och implementeringsmetoder

Adobe erbjuder flera sätt att implementera Adobe Analytics. På varje sida finns ett avsnitt om hur du implementerar variabeln med Web SDK, med tillägget Adobe Analytics, och hur du använder AppMeasurement för JavaScript.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konfigurera variabler](https://video.tv.adobe.com/v/3456976?quality=12&learn=on&captions=swe){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Operationsordning

AppMeasurement-bibliotek som publiceras av Adobe Analytics följer en viss ordning när data skickas till Adobe. Om du utför dessa åtgärder i fel ordning kan data vara ofullständiga.

1. Om webbplatsen använder ett datalager måste du se till att alla tillämpliga variabler fylls i först. Du kan till exempel fylla i `adobeDataLayer.page.title` med sidrubriken. Mer information finns i [Datalager](../prepare/data-layer.md).
2. Använd datalagret för att fylla i Analytics-variabler. <br/>Om du använder taggar i Adobe Experience Platform utförs den här uppgiften med dataelement däremellan. Dataelement fylls med värden från datalagret. Dataelementet `Page Title` hämtar till exempel värdet från datalagervariabeln `adobeDataLayer.page.title`. <br/>Sedan kan du använda dataelementet för att fylla i Analytics-variabler. `eVar4` hämtar till exempel värdet från dataelementet `Page Title`. <br/>Mer information finns i [Dataelement](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=sv-SE), [Mappa datalagretobjekt till dataelement](../launch/layer-to-elements.md) och [Mappa taggelement till analysvariabler](../launch/elements-to-variable.md)
3. Anropa till sist spårningsfunktionen. De flesta AppMeasurement-bibliotek använder metoden `t()`, men vissa SDK-mobiler använder `track()`. När spårningsfunktionen anropas skickas alla variabler som stöds i Analytics-objektet till Adobe i form av en bildbegäran.

## Ogiltiga tecken

Följande tecken och strängar tillåts aldrig i JavaScript-variabler.

* Tabb (`0x09`)
* Radretur (`0x0D`)
* Tidslinje (`0x0A`)
* HTML-taggar (t.ex. `<b></b>` eller `&#153`)

Vissa variabler har ytterligare begränsningar eller syntaxkrav. Variabeln [`products`](page-vars/products.md) reserverar t.ex. semikolon och kommatecken som avgränsar olika produkter och kategorier.
