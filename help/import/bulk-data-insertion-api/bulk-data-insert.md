---
title: API för insättning av data i bulk
description: BDIA (Bulk Data Insertion API) är en Adobe Analytics-funktion som gör att du kan överföra serveranropsdata i grupper av filer i stället för att använda klientbibliotek som AppMeasurement. Serveranropen i dessa gruppfiler kan antingen vara aktuella (livedata) eller historiska data. Det är en mer skalbar efterföljare till API:t för datainfogning i tidigare versioner av Adobe Analytics API.
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 8%

---


# API för insättning av data i bulk

Inmatning av massdata löser flera problem, t.ex.:

* Inhämta historiska data från ett tidigare analyssystem

* Ett internt analyssamlingssystem som gör det omöjligt att använda AppMeasurement. Du kan använda ETL-processer (Extract-Transform-Load) för att lägga in data i gruppfiler och sedan använda BDIA för att överföra dem till Adobe Analytics.

* Datainsamling från enheter som bara har intermittent anslutning till Internet. De här enheterna lagrar interaktionerna tills de får en anslutning. Enheten kan sedan överföra alla data på en gång via BDIA.

API för datainfogning och [API för massdatainmatning](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)båda är metoder för att skicka data från serversidessamlingar till Adobe Analytics. API-anrop för datainfogning görs en händelse i taget. API för datainfogning i grupp accepterar CSV-formaterade filer som innehåller händelsedata, en händelse per rad. Om du arbetar med en ny implementering av en serversidessamling rekommenderar vi att du använder API:t för datainfogning i grupp.