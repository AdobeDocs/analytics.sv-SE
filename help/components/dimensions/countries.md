---
title: Länder
description: Det land som träffen härstammar från.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Länder

Länderna [dimension](overview.md) rapporterar det land där träffen kom. Den här dimensionen är användbar för att avgöra vilka länder besökarna mest besöker när de besöker er webbplats. Ni kan använda dessa data för att fokusera på marknadsföringen i dessa länder eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adress och land.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Geo Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Dimensioner omfattar länder över hela världen. Exempelvärden innehåller `"United States"`, `"United Kingdom"`, eller `"India"`.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **IP-adresser för mobiler**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Vissa transportföretag backar tillbaka IP-trafiken genom centraliserade eller regionala närvaroplatser.
* **Användare av satelliter**: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som skymmer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
