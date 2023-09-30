---
title: USA
description: Besökarens tillstånd i USA.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# USA

USA-staten [dimension](overview.md) rapporterar besökarens tillstånd i USA. Det liknar [Regioner](regions.md) -dimension, förutom att denna dimension är specifik för USA. Att använda den här dimensionen är värdefullt om du vill ha mer detaljerad information än [Länder](countries.md) men inte så granulerande som [Städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adress och land.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Geo Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Dimensioner är bland annat regioner och det land som  bor i. Exempelvärden innehåller `"California"`, `"Texas"`, eller `"Virginia"`. Dimensionsartikeln `"Unspecified"` omfattar all internationell trafik utanför USA.

Den här dimensionen kan innehålla `"AOL"`, en Internetleverantör. Prenumeranter på den här tjänsten har tilldelats en åtkomstpunkt. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geolokalisering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Vissa transportföretag backar tillbaka IP-trafiken genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som skymmer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
