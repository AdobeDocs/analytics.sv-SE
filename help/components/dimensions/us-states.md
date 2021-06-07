---
title: USA
description: Besökarens tillstånd i USA.
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# USA

I USA-dimensionen rapporteras besökarens tillstånd i USA. Den liknar dimensionen [Områden](regions.md), förutom att den här dimensionen är specifik för USA. Det är värdefullt att använda den här dimensionen om du vill ha mer detaljerad information än [Länder](countries.md), men inte så detaljerad som [Städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adresser och länder. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Dimensioner är bland annat regioner och det land som regionen bor i. Exempelvärden är `"California"`, `"Texas"` eller `"Virginia"`. Dimensionsobjektet `"Unspecified"` innehåller all internationell trafik utanför USA.

Denna dimension kan omfatta `"AOL"`, en Internetleverantör för uppringd anslutning. Prenumeranter på den här tjänsten har tilldelats en åtkomstpunkt. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geopositionering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
