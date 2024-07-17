---
title: API för insättning av data i bulk
description: BDIA (Bulk Data Insertion API) är en Adobe Analytics-funktion som gör att du kan överföra serveranropsdata i grupper av filer i stället för att använda klientbibliotek som AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# API för insättning av data i bulk

Inmatning av massdata löser flera problem, t.ex.:

* Inhämta historiska data från ett tidigare analyssystem

* Ett internt analysinsamlingssystem som gör det omöjligt att använda AppMeasurement. Du kan använda ETL-processer (Extract-Transform-Load) för att lägga in data i gruppfiler och sedan använda BDIA för att överföra dem till Adobe Analytics.

* Datainsamling från enheter som bara har intermittent anslutning till Internet. De här enheterna lagrar interaktionerna tills de får en anslutning. Enheten kan sedan överföra alla data på en gång via BDIA.

API för datainfogning och [API för datainfogning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) är båda metoder för att skicka data från serversidan till Adobe Analytics. API-anrop för datainfogning görs en händelse i taget. API för datainfogning i grupp accepterar CSV-formaterade filer som innehåller händelsedata, en händelse per rad. Om du arbetar med en ny implementering av en serversidessamling rekommenderar vi att du använder API:t för datainfogning i grupp.
