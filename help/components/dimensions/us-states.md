---
title: USA
description: Besökarens tillstånd i USA.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# USA

I USA-dimensionen rapporteras besökarens tillstånd i USA. Det liknar [Regioner](regions.md) -dimension, förutom att denna dimension är specifik för USA. Att använda den här dimensionen är värdefullt om du vill ha mer detaljerad information än [Länder](countries.md) men inte så granulerande som [Städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adress och land. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Dimensioner är bland annat regioner och det land som regionen bor i. Exempelvärden innehåller `"California"`, `"Texas"`, eller `"Virginia"`. Dimensionsartikeln `"Unspecified"` omfattar all internationell trafik utanför USA.

Denna dimension kan innehålla `"AOL"`, en Internetleverantör. Prenumeranter på den här tjänsten har tilldelats en åtkomstpunkt. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geopositionering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
