---
title: Städer
description: Staden där träffen kom från.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Städer

Städerna [dimension](overview.md) rapporterar staden som träffen kommer från. Den här dimensionen är användbar för att avgöra vilka de populäraste städerna besökarna kommer från när de besöker din webbplats. Ni kan använda dessa data för att fokusera på lokal annonsering i dessa städer, som affischtavlor och reklamfilmer.

## Fyll den här dimensionen med data

Den här dimensionen refererar till uppslagsregler som är interna för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adressen och staden.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Geo Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE) för Web SDK-implementeringar.

## Dimensioner

Dimensioner omfattar städer över hela världen. Exempelvärden är `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` eller `"London (London, United Kingdom)"`.

Vissa dimensionsobjekt kan innehålla `"AOL"`, en Internetleverantör för uppringd anslutning. Prenumeranter på den här tjänsten tilldelas en åtkomstpunkt baserat på det land där deras kontonummer är etablerat. AOL-användare använder IP-adressen för den här åtkomstpunkten. Eftersom den här dimensionen baseras på IP-adressen används åtkomstpunktens geolokalisering i stället för besökarens faktiska plats.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Vissa transportföretag backar tillbaka IP-trafiken genom centraliserade eller regionala närvaroplatser.
* **Användare av satellitbaserade Internet-leverantörer**: Det är svårt att identifiera dessa användares specifika plats eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighets-IP:n**: Representerar personal som reser runt i världen och går genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
* **Proxies som döljer IP-adresser av sekretesskäl**: Tjänster som Apple Private Relay döljer den sanna IP-adressen genom att skicka data slumpmässigt via en mellanhand eller proxy. Den här proxyn ersätter sedan en annan IP-adress innan den vidarebefordras till Adobe.
