---
title: Regioner
description: Besökarens geografiska region.
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Regioner

Regionerna [dimension](overview.md) rapporterar besökarens geografiska region. Det är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. Att använda den här dimensionen är värdefullt om du vill ha mer detaljerad information än [Länder](countries.md) men inte så granulerande som [Städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adress och land. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Dimensioner är bland annat regioner och det land som  bor i. Exempelvärden innehåller `"California (United States)"`, `"Tokyo (Japan)"`, eller `"Sao Paulo (Brazil)"`.

Vissa dimensionsobjekt kan innehålla `"AOL"`, en Internetleverantör. Prenumeranter på den här tjänsten tilldelas en åtkomstpunkt baserat på det land där deras kontonummer är etablerat. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geolokalisering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som skymmer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
