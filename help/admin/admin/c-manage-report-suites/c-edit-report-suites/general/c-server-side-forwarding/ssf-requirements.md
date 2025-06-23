---
description: För att implementera vidarebefordran på serversidan måste du uppfylla dessa krav för Experience Cloud-lösningar, -tjänster och -kod. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du kan hämta de senaste kodbiblioteken.
solution: Analytics
title: Krav för vidarebefordran på serversidan
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 0%

---

# Krav för vidarebefordran på serversidan

För att implementera vidarebefordran på serversidan måste du uppfylla dessa krav för Experience Cloud-lösningar, -tjänster och -kod. Dessa krav innehåller även anvisningar om hur du söker efter kodversioner och var du kan hämta de senaste kodbiblioteken.

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

Alla verktyg som övervakar HTTP-begäranden som görs av en webbläsare kan visa versionsnumret för din AppMeasurement- och Visitor-API-kod. `AppMeasurement_Module_AudienceManagement.js` innehåller inte eller returnerar något versions-ID. I följande exempel visas hur version-ID:n för `AppMeasurement.js` och `VisitorAPI.js`-kod ser ut.

* `AppMeasurement.js`: [Adobe Debugger](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html) returnerar AppMeasurement-versionen så här: `Version of Code | JS-1.5.1`. Andra verktyg kan använda en annan etikett, men värdet följer alltid mönstret `JS-X.X.X`, där `X` är ett versionsnummer.
* `VisitorAPI.js`: Leta efter parametern `d_visid_ver`. Du kommer att få se besökar-ID-tjänsten så här: `d_visid_ver: 1.5.5`. API-kod för besökare som är äldre än version 1.5.2 innehöll inget versionsnummer. Du använder antagligen ett äldre kodbibliotek (och behöver uppgradera) om övervakningsresultaten inte returnerar något versionsnummer.
