---
title: Analysera marknadsföringskanaler
description: Lär dig hur du använder dimensionerna för marknadsföringskanaler i Workspace.
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# Analysera marknadsföringskanaler

>[!NOTE]
>
>För att maximera effekten av marknadsföringskanaler för attribuering och Customer Journey Analytics har vi publicerat [reviderade best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Analysadministratörer kan hantera marknadsföringskanaler för sina organisationer enligt beskrivningen i [Hantera marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Ni vill antagligen veta vilka av era marknadsföringskanaler som är mest effektiva och med vilka ni kan inrikta er bättre och få bättre avkastning på era marknadsföringsinvesteringar. I Adobe Analytics är Marketing Channel-kanalens mått och mätvärden i Workspace ett av de verktyg som kan hjälpa er att spåra hur olika kanaler påverkar era order, intäkter osv. och ge er användbara kanalinsikter. Här är de mått och mätvärden du kan använda för marknadsföringskanaler:

![](assets/mc-dims.png)

| Dimension/mått | Definition |
| --- | --- |
| Marknadsföringskanal | Det här är den rekommenderade dimensionen för marknadsföringskanaler som ska användas. Attributionsmodeller kan användas vid körning. Den här dimensionen fungerar på samma sätt som den sista beröringskanalen, men den har en annan etikett för att förhindra förvirring när den används med en annan attribueringsmodell. |
| Senaste beröringskanal | Äldre dimension, med den senaste pekattribueringsmodellen förtillämpad och oföränderlig. |
| Första beröringskanalen | Äldre dimension, med första pekattribueringsmodellen förtillämpad och oföränderlig. |
| Instanser för marknadsföringskanal | Detta mått mäter hur många gånger en marknadsföringskanal definierades i en bildbegäran, inklusive standardsidvisningar och anpassade länkanrop. Inkluderar inte beständiga värden. |
| Nya åtaganden | Det här måttet liknar förekomster, men ökas bara när den första pekmarknadsföringskanalen definieras i en bildbegäran. |

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

Du kan använda [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) för att tillämpa olika attribueringsmodeller direkt:

![](assets/mc-viz5.png)

Lägg märke till hur samma mått (onlineorder) genererar olika resultat när du använder olika attribueringsmodeller.

## Flerfliksanalys

Med den äldre First Touch Channel och Last Touch Channel kan du få en användbar bild av kanalinteraktionen:

![](assets/mc-viz6.png)

Lär dig mer om tabbbaserad marknadsanalys i den här videon: [Använda tabbanalys för att utforska grundläggande marknadsattribuering i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html).
