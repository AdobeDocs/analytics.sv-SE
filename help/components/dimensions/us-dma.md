---
title: US DMA
description: Marknadsområdet för träffen.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# US DMA

I dimensionen &#39;US DMA&#39; rapporteras besökarens utsedda marknadsområde (DMA). Det bygger på mediemarknader som sammanställts av [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med Nielsen för att upprätthålla sökningar mellan IP-adressen och DMA. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Bland Dimensionerna finns besökarens DMA- och DMA-kod. Den tresiffriga koden är inte ett postnummer, utan DMA-koden från Nielsen. Exempelvärden innehåller `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, eller `"Los Angeles (803)"`. Dimensionsartikeln `"No Metro (0)"` omfattar all internationell trafik utanför USA.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
