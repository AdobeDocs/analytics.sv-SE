---
title: Punkter
description: Antalet träffar som matchade båda reglerna.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Punkter

&#39;Bot instances&#39; [mått](overview.md) visar antalet träffar som matchar [Punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Eftersom båda rapporterna är åtskilda från resten av rapportsvitens data fungerar dessa mått bara med följande dimensioner:

* [Punktnamn](../dimensions/bot-name.md)
* [Sida](../dimensions/page.md)
* Tidsbaserade dimensioner (till exempel [Dag](../dimensions/day.md), [Vecka](../dimensions/week.md), eller [Månad](../dimensions/month.md))

Om du använder någon annan dimension med det här måttet returneras inga data.

## Hur det här måttet beräknas

Adobe kontrollerar varje träff för att se om det matchar båda reglerna som din organisation har konfigurerat. Om en given träff matchar en robotregel, utesluts träffen från rapporteringen och detta mätvärde ökar med ett. Det här måttet innehåller båda sidvyerna ([`t()`](/help/implement/vars/functions/t-method.md)) och länkspårningsträffar ([`tl()`](/help/implement/vars/functions/tl-method.md)). [Bot page views](bot-page-views.md) innehåller inga träffar för länkspårning.
