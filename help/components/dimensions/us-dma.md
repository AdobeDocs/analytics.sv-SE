---
title: US DMA
description: Marknadsområdet för träffen.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# US DMA

&#39;US DMA&#39; [dimension](overview.md) rapporterar besökarens utsedda marknadsområde. Det bygger på mediemarknader som sammanställts av [Nielsen](https://www.nielsen.com/dma-regions/).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med Nielsen för att upprätthålla sökningar mellan IP-adressen och DMA.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Geo Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Dimensionen omfattar besökarens DMA- och DMA-koder. Den tresiffriga koden är inte ett postnummer, utan DMA-koden från Nielsen. Exempelvärden innehåller `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, eller `"Los Angeles (803)"`. Dimensionsartikeln `"No Metro (0)"` omfattar all internationell trafik utanför USA.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Vissa transportföretag backar tillbaka IP-trafiken genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som skymmer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
