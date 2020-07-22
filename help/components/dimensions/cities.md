---
title: Städer
description: Staden där träffen kom från.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---


# Städer

Dimensionen Städer rapporterar staden som träffen härstammar från. Den här dimensionen är användbar för att avgöra vilka de populäraste städerna besökarna kommer från när de besöker din webbplats. Ni kan använda dessa data för att fokusera på lokal annonsering i dessa städer, som affischtavlor och reklamfilmer.

## Fyll den här dimensionen med data

Den här dimensionen refererar till interna uppslagsregler för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adresser och ort. Den här dimensionen fungerar som den ska för alla implementeringar.

>[!TIP]
>
>Om din organisation följer strikta sekretessregler där det inte räcker med att [komplicera IP-adressen](/help/admin/admin/general-acct-settings-admin.md) kan du begära att få inaktivera geopositioneringsdata helt och hållet. Kontakta kundtjänst med rapportsvitens ID och be att få stänga av Geography för rapportsviten.

## Dimensionsobjekt

Dimensionsobjekten omfattar städer över hela världen. Exempelvärdena inkluderar `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"`eller `"London (London, United Kingdom)"`.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
