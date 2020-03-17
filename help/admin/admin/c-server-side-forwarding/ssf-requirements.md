---
description: Du måste uppfylla dessa krav på Experience Cloud-lösning, -tjänst och -kod för att kunna implementera vidarebefordran på serversidan. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du ska hämta de senaste kodbiblioteken.
solution: Audience Manager
title: Krav för vidarebefordran på serversidan
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Krav för vidarebefordran på serversidan

Du måste uppfylla dessa krav på Experience Cloud-lösning, -tjänst och -kod för att kunna implementera vidarebefordran på serversidan. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du ska hämta de senaste kodbiblioteken.

## Lösningskrav

Vidarebefordran på serversidan fungerar med [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) och [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) och/eller [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Tjänstkrav

Vidarebefordran på serversidan kräver [identitetstjänsten](https://marketing.adobe.com/resources/help/en_US/mcvid/). Identitetstjänsten tillhandahåller ett universellt ID som identifierar webbplatsbesökare över alla lösningar i Experience Cloud. Du måste implementera ID-tjänsten innan vidarebefordran på serversidan fungerar.

## Kodversioner

Vidarebefordran på serversidan kräver version 1.5 (eller senare) av kodbiblioteken som listas nedan. Vi rekommenderar att du använder de senaste versionerna i stället för att använda de här minimikraven.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Kontrollera kodbiblioteksversionen

Alla verktyg som övervakar HTTP-begäranden som görs av en webbläsare kan visa versionsnumret för API-koden för AppMeasurement och Visitor. Den `AppMeasurement_Module_AudienceManagement.js` innehåller inte eller returnerar något versions-ID. I följande exempel visas hur version-ID:n för `AppMeasurement.js` och `VisitorAPI.js` kod ser ut.

* `AppMeasurement.js`: [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) returnerar AppMeasurement-versionen så här: `Version of Code | JS-1.5.1`. Andra verktyg kan använda en annan etikett, men värdet följer alltid mönstret `JS-X.X.X`där `X` är ett versionsnummer.
* `VisitorAPI.js`: Leta efter `d_visid_ver` parametern. Du får då se besökar-ID-tjänsten så här: `d_visid_ver: 1.5.5`. API-kod för besökare som är äldre än version 1.5.2 innehöll inget versionsnummer. Du använder antagligen ett äldre kodbibliotek (och behöver uppgradera) om övervakningsresultaten inte returnerar något versionsnummer.
