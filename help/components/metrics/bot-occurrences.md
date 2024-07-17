---
title: Punkter
description: Antalet träffar som matchade båda reglerna.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Punkter

[Mätvärdet ](overview.md) för &#39;Bot-förekomster&#39; visar antalet träffar som matchade [Bot-regler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Eftersom båda rapporterna är åtskilda från resten av rapportsvitens data fungerar dessa mått bara med följande dimensioner:

* [Punktnamn](../dimensions/bot-name.md)
* [Sida](../dimensions/page.md)
* Tidsbaserade dimensioner (till exempel [Dag](../dimensions/day.md), [Vecka](../dimensions/week.md) eller [Månad](../dimensions/month.md))

Om du använder någon annan dimension med det här måttet returneras inga data.

## Hur det här måttet beräknas

Adobe kontrollerar varje träff för att se om det matchar båda reglerna som din organisation har konfigurerat. Om en given träff matchar en robotregel, utesluts träffen från rapporteringen och detta mätvärde ökar med ett. Det här måttet innehåller både sidvyer ([`t()`](/help/implement/vars/functions/t-method.md)) och länkspårningsträffar ([`tl()`](/help/implement/vars/functions/tl-method.md)), medan [Bot-sidvyer ](bot-page-views.md) inte innehåller länkspårningsträffar.
