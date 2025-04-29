---
title: Det gick inte att hitta sidor (dimensioner)
description: URL:er som returnerade ett fel på din plats.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 828f41bf45c1954c3b68ad71a7746e24626b9eed
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Sidorna hittades inte

*Den här hjälpsidan beskriver hur &quot;Sidor som inte hittas&quot; fungerar som en [dimension](overview.md). Gå till sidan [Sidor som inte hittas](../metrics/pages-not-found.md) om du vill ha information om hur den fungerar som ett mått.*

Dimensionen &quot;Sidor som inte hittas&quot; visar URL:er som innehåller ett fel. Den här dimensionen är användbar när du vill minska antalet fel som besökare får på din webbplats.

* Du kan använda den här dimensionen i en [Flödesvisualisering](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) för att se vilka sidor besökarna klickar igenom för att komma till felet. Du kan sedan arbeta med utvecklingsteam i organisationen för att åtgärda länken på varje sida.
* Du kan använda den här dimensionen med dimensionen [&#39;Referer&#39;](referrer.md) för att se var besökare kommer till din webbplats från externa länkar. Du kan sedan antingen implementera omdirigeringar till önskad plats eller arbeta med tredje part för att få länken åtgärdad.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageType` och `g` frågesträngar ](/help/implement/validate/query-parameters.md) i bildbegäranden. Om frågesträngen `pageType` är lika med `errorPage` spelas frågesträngen `g` in. AppMeasurement samlar in dessa data med variabeln [`pageType`](/help/implement/vars/page-vars/pagetype.md). Om variabeln `pageType` inte är definierad eller inställd på något annat än `errorPage` samlas inga data för den här dimensionen in.

## Dimension-objekt

Dimension-objekten innehåller URL:er för de sidor på webbplatsen där ett fel inträffade.
