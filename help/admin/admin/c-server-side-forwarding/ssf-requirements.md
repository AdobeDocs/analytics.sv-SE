---
description: För att implementera vidarebefordran på serversidan måste du uppfylla dessa krav för Experience Cloud, service och kod. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du ska hämta de senaste kodbiblioteken.
solution: Audience Manager
title: Krav för vidarebefordran på serversidan
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Krav för vidarebefordran på serversidan

För att implementera vidarebefordran på serversidan måste du uppfylla dessa krav för Experience Cloud, service och kod. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du ska hämta de senaste kodbiblioteken.

## Lösningskrav

Vidarebefordran på serversidan fungerar med [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) och [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) och/eller [Publiker](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html).

## Tjänstkrav

Vidarebefordran på serversidan kräver [identitetstjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html). Identitetstjänsten tillhandahåller ett universellt ID som identifierar webbplatsbesökare över alla lösningar i Experience Cloud. Du måste implementera ID-tjänsten innan vidarebefordran på serversidan fungerar.

## Kodversioner

Vidarebefordran på serversidan kräver version 1.5 (eller senare) av kodbiblioteken som listas nedan. Vi rekommenderar att du använder de senaste versionerna i stället för att använda de här minimikraven.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Kontrollera kodbiblioteksversionen

Alla verktyg som övervakar HTTP-begäranden som görs av en webbläsare kan visa versionsnumret för API-koden för AppMeasurement och Visitor. `AppMeasurement_Module_AudienceManagement.js` innehåller inte eller returnerar något versions-ID. I följande exempel visas hur version-ID:n för `AppMeasurement.js` och `VisitorAPI.js`-kod ser ut.

* `AppMeasurement.js`: Felsökningsfunktionen  [Adobe ](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html) returnerar AppMeasurement-versionen så här:  `Version of Code | JS-1.5.1`. Andra verktyg kan använda en annan etikett, men värdet följer alltid mönstret `JS-X.X.X`, där `X` är ett versionsnummer.
* `VisitorAPI.js`: Leta efter  `d_visid_ver` parametern. Du får då se besökar-ID-tjänsten så här: `d_visid_ver: 1.5.5`. API-kod för besökare som är äldre än version 1.5.2 innehöll inget versionsnummer. Du använder antagligen ett äldre kodbibliotek (och behöver uppgradera) om övervakningsresultaten inte returnerar något versionsnummer.
