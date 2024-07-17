---
title: US DMA
description: Marknadsområdet för träffen.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# US DMA

USA:s DMA:n [dimension](overview.md) rapporterar besökarens utsedda marknadsområde (DMA). Den baseras på mediemarknader som har kompilerats av [Nielsen](https://www.nielsen.com/dma-regions/).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med Nielsen för att upprätthålla sökningar mellan IP-adressen och DMA.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Geo Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) för Web SDK-implementeringar.

## Dimensioner

Dimensionen omfattar besökarens DMA- och DMA-koder. Den tresiffriga koden är inte ett postnummer, utan DMA-koden från Nielsen. Exempelvärden är `"Dallas-Ft. Worth (623)"`, `"New York (501)"` eller `"Los Angeles (803)"`. Dimensionsobjektet `"No Metro (0)"` innehåller all internationell trafik utanför USA.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Vissa transportföretag backar tillbaka IP-trafiken genom centraliserade eller regionala närvaroplatser.
* **Användare av satellitbaserade Internet-leverantörer**: Det är svårt att identifiera dessa användares specifika plats eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighets-IP:n**: Representerar personal som reser runt i världen och går genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som döljer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
