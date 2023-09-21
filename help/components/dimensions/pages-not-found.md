---
title: Det gick inte att hitta sidor (dimensioner)
description: URL:er som returnerade ett fel på din plats.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som en [dimension](overview.md). Se [Sidorna hittades inte](../metrics/pages-not-found.md) för mer information.*

Dimensionen &quot;Sidor som inte hittas&quot; visar URL:er som innehåller ett fel. Den här dimensionen är användbar när du vill minska antalet fel som besökaren får på din webbplats.

* Du kan använda den här dimensionen i en [Flödesvisualisering](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) för att se vilka sidor besökarna klickar igenom för att hitta felet. Du kan sedan arbeta med utvecklingsteam i organisationen för att åtgärda länken på varje sida.
* Du kan använda den här dimensionen med [&#39;Referent&#39;](referrer.md) dimension för att se var besökarna kommer till din webbplats från externa länkar. Du kan sedan antingen implementera omdirigeringar till önskad plats eller arbeta med tredje part för att få länken åtgärdad.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageType` och `g` frågesträngar](/help/implement/validate/query-parameters.md) i bildbegäranden. Om `pageType` frågesträng är lika med `errorPage`, `g` frågesträng (sid-URL) spelas in. AppMeasurementet samlar in dessa data med [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabel. Om `pageType` variabeln är inte definierad eller inställd på något annat än `errorPage`, samlas inga data in för den här dimensionen.

## Dimensioner

Bland Dimensionerna finns URL:er för de sidor på webbplatsen där ett fel uppstod.
