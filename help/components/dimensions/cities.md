---
title: Städer
description: Staden där träffen kom från.
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Städer

Dimensionen Städer rapporterar staden som träffen härstammar från. Den här dimensionen är användbar för att avgöra vilka de populäraste städerna besökarna kommer från när de besöker din webbplats. Ni kan använda dessa data för att fokusera på lokal annonsering i dessa städer, som affischtavlor och reklamfilmer.

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adressen och staden. Den här dimensionen fungerar som den ska för alla implementeringar.

## Dimensioner

Dimensioner omfattar städer över hela världen. Exempelvärden är `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` eller `"London (London, United Kingdom)"`.

Vissa dimensionsobjekt kan innehålla `"AOL"`, en Internetleverantör för uppringd anslutning. Prenumeranter på den här tjänsten tilldelas en åtkomstpunkt baserat på det land där deras kontonummer är etablerat. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geopositionering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: IP-målanpassning för mobiler fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
