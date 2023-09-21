---
title: Bot page views
description: Antalet sidvyer som matchar båda reglerna.
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Bot page views

Vyer för startsidan [mått](overview.md) visar antalet sidträffar som matchar [Punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Eftersom båda rapporterna är åtskilda från resten av rapportsvitens data fungerar dessa mått bara med följande dimensioner:

* [Punktnamn](../dimensions/bot-name.md)
* [Sida](../dimensions/page.md)
* Tidsbaserade dimensioner (till exempel [Dag](../dimensions/day.md), [Vecka](../dimensions/week.md), eller [Månad](../dimensions/month.md))

Om du använder någon annan dimension med det här måttet returneras inga data.

## Hur det här måttet beräknas

Adobe kontrollerar varje sidträff för att se om det matchar båda reglerna som din organisation har konfigurerat. Om en given träff matchar en robotregel, utesluts sidträffen från rapporteringen och detta mätvärde ökas med ett. Det här måttet inkluderar inte länkspårningstips ([`tl()`](/help/implement/vars/functions/tl-method.md)).
