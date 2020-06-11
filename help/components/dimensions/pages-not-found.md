---
title: Sidorna hittades inte
description: URL:er som returnerade ett fel på din plats.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# Sidorna hittades inte

*Den här hjälpsidan beskriver hur&quot;Sidor som inte hittas&quot; fungerar som en dimension. Mer information finns i måtten för[Sidor som inte hittas](../metrics/pages-not-found.md).*

Dimensionen &quot;Sidor som inte hittas&quot; visar URL:er som innehåller ett fel. Den här dimensionen är användbar när du vill minska antalet fel som besökaren får på din webbplats.

* Du kan använda den här dimensionen i en [flödesvisualisering](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) för att se vilka sidor besökarna klickar igenom för att hitta felet. Du kan sedan arbeta med utvecklingsteam i organisationen för att åtgärda länken på varje sida.
* Du kan använda den här dimensionen med [referensdimensionen](referrer.md) för att se var besökarna kommer till din webbplats från externa länkar. Du kan sedan antingen implementera omdirigeringar till önskad plats eller arbeta med tredje part för att få länken åtgärdad.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`pageType` - och `g` frågesträngarna](/help/implement/validate/query-parameters.md) i bildbegäranden. Om `pageType` frågesträngen är lika med `errorPage`, spelas `g` frågesträngen (sid-URL) in. AppMeasurement samlar in dessa data med hjälp av [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabeln. Om `pageType` variabeln inte är definierad eller inställd på något annat än `errorPage`samlas inga data för den här dimensionen in.

## Dimensionsvärden

Dimensionsvärdena innehåller URL:er för sidorna på webbplatsen där ett fel uppstod.
