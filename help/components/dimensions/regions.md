---
title: Regioner
description: Besökarens geografiska region.
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: 4e09df2631626376f9351512afed7a9e4241e7d6
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Regioner

Dimensionen &#39;Regioner&#39; rapporterar besökarens geografiska region. Det är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. Det är värdefullt att använda den här dimensionen om du vill ha mer detaljerad information än [Länder](countries.md), men inte så detaljerad som [Städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adresser och länder. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Dimensioner är bland annat regioner och det land som regionen bor i. Exempelvärden är `"California (United States)"`, `"Tokyo (Japan)"` eller `"Sao Paulo (Brazil)"`.

Vissa dimensionsobjekt kan innehålla `"AOL"`, en Internetleverantör för uppringd anslutning. Prenumeranter på den här tjänsten tilldelas en åtkomstpunkt baserat på det land där deras kontonummer är etablerat. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geopositionering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
