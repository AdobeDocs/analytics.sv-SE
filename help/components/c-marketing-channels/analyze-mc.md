---
title: Analysera marknadsföringskanaler
description: Lär dig hur du använder dimensionerna för marknadsföringskanaler i arbetsytan.
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---


# Analysera marknadsföringskanaler

Ni vill antagligen veta vilka av era marknadsföringskanaler som är mest effektiva och med vilka ni kan inrikta er bättre och få bättre avkastning på era marknadsföringsinvesteringar. I Adobe Analytics är dimensionerna och måtten för marknadsföringskanalerna i Workspace ett av verktygen som kan hjälpa er att spåra olika kanalers påverkan på era order, intäkter osv. och ge er användbara kanalinsikter. Här är de mått och mätvärden du kan använda för marknadsföringskanaler:

![](assets/mc-dims.png)

| Dimension/mått | Definition |
|---|---|
| Marknadsföringskanal | Detta är den rekommenderade dimensionen för marknadsföringskanaler som ska användas. Attribution IQ kan tillämpas på dem vid körning. Den här dimensionen fungerar på samma sätt som den sista beröringskanalen, men den har en annan etikett för att förhindra förvirring när den används med en annan attribueringsmodell. |
| Senaste beröringskanal | Äldre dimension, med den senaste pekattribueringsmodellen förtillämpad och oföränderlig. |
| Första beröringskanalen | Äldre dimension, med första pekattribueringsmodellen förtillämpad och oföränderlig. |
| Instanser för marknadsföringskanal | Detta mått mäter hur många gånger en marknadsföringskanal definierades i en bildbegäran, inklusive standardsidvisningar och anpassade länkanrop. Inkluderar inte beständiga värden. |
| Nya åtaganden | Det här måttet liknar instanser, men ökas bara när den första pekmarknadsföringskanalen definieras i en bildbegäran. |

## Grundläggande analys

I den här frihandstabellen visas mått för onlineorder, onlineintäkter och konverteringsgraden för var och en av marknadsföringskanalerna:

![](assets/mc-viz1.png)

Här ser du varje Marketing Channel-kanals onlinebeställningar och onlineintäkter i ett diagram:

![](assets/mc-viz2.png)

I det här linjediagrammet visas trender i onlinebeställningar för olika kanaler över tid:

![](assets/mc-viz3.png)

## Avancerad analys

Marknadsföringskanaler Detaljerna rör sig djupare in i varje kanal för att visa specifika kampanjer, placeringar osv. Du kan dela upp varje marknadsföringskanal i detaljer:

![](assets/mc-viz4.png)

## Använd attribueringsmodeller

Du kan använda [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/use-attribution.html) för att tillämpa olika attribueringsmodeller direkt:

![](assets/mc-viz5.png)

Lägg märke till hur samma mått (onlineorder) genererar olika resultat när du använder olika attribueringsmodeller.

## Flerfliksanalys

Med den äldre First Touch Channel och Last Touch Channel får du en användbar vy över kanalinteraktionerna:

![](assets/mc-viz6.png)

Läs mer om flerfliksanalys i den här videon: [Utforska grundläggande marknadsattribuering i Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html)med hjälp av flikanalys.
