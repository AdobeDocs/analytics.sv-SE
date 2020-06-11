---
title: US DMA
description: Marknadsområdet för träffen.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# US DMA

I dimensionen &#39;US DMA&#39; rapporteras besökarens utsedda marknadsområde (DMA). Den bygger på mediemarknader som [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/)sammanställt.

## Fyll den här dimensionen med data

Den här dimensionen refererar till interna uppslagsregler för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med Nielsen för att upprätthålla sökningar mellan IP-adressen och DMA. Den här dimensionen fungerar som den ska för alla implementeringar.

> [!TIP] Om din organisation följer strikta sekretessregler där det inte räcker med att [komplicera IP-adressen](/help/admin/admin/general-acct-settings-admin.md) kan du begära att få inaktivera geopositioneringsdata helt och hållet. Kontakta kundtjänst med rapportsvitens ID och be att få stänga av Geography för rapportsviten.

## Dimensionsvärden

Dimensionsvärdena inkluderar besökarens DMA- och DMA-kod. Den tresiffriga koden är inte ett postnummer, utan DMA-koden från Nielsen. Exempelvärdena inkluderar `"Dallas-Ft. Worth (623)"`, `"New York (501)"`eller `"Los Angeles (803)"`. Dimensionsvärdet `"No Metro (0)"` omfattar all internationell trafik utanför USA.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
