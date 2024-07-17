---
title: Punktnamn
description: Namnet på roboten som matchade batchregler.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# Punktnamn

&quot;Punktnamn&quot; [dimension](overview.md) visar namnen på de objekt som har identifierats med [punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Dessa regler kan vara standard-IAB-regler eller anpassade robotregler som din organisation konfigurerar. Det är praktiskt om du vill veta mer om vilka botar som besöker er webbplats eller vilka botar som genererar mest trafik.

Träffar som matchar [!UICONTROL Bot rules] filtreras automatiskt bort från alla analysrapporter med undantag för den här dimensionen, [Bot-förekomster](../metrics/bot-occurrences.md) och [Bot-sidvyer](../metrics/bot-page-views.md). Ni kan använda den här dimensionen och dessa två mätvärden för att se vilka båda data som är exkluderade från resten av era rapporter.

Eftersom båda rapporterna är åtskilda från resten av rapportsvitens data stöds endast följande mått och mätvärden med den här dimensionen:

* [Sida](page.md)
* Tidsbaserade dimensioner (till exempel [Dag](day.md), [Vecka](week.md) eller [Månad](month.md))
* [Punkter](../metrics/bot-occurrences.md)
* [Bot page views](../metrics/bot-page-views.md)

Om du använder andra mått eller mätvärden med den här dimensionen returneras inga data.

## Fyll den här dimensionen med data

Om du har aktiverat [Punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) samlar den här dimensionen automatiskt in data. Om du ännu inte har aktiverat [!UICONTROL Bot rules] visas inte den här dimensionen i Analysis Workspace.

## Dimensioner

Varje dimensionsobjekt visar namnet på roboten som matchade IAB- eller anpassade robotregelvillkor.
