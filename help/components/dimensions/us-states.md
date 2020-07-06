---
title: USA
description: Besökarens tillstånd i USA.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# USA

I USA-dimensionen rapporteras besökarens tillstånd i USA. Den liknar dimensionen [Regioner](regions.md) , förutom att denna dimension är specifik för USA. Det är värdefullt att använda den här dimensionen om du vill ha mer detaljerad information än [länder](countries.md) , men inte så detaljerad som [städer](cities.md).

## Fyll den här dimensionen med data

Den här dimensionen refererar till interna uppslagsregler för Adobe. Uppslagsvärdet baseras på den IP-adress som skickades med träffen. Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att upprätthålla sökningar mellan IP-adresser och länder. Den här dimensionen fungerar som den ska för alla implementeringar.

>[!TIP]
>
>Om din organisation följer strikta sekretessregler där det inte räcker med att [komplicera IP-adressen](/help/admin/admin/general-acct-settings-admin.md) kan du begära att få inaktivera geopositioneringsdata helt och hållet. Kontakta kundtjänst med rapportsvitens ID och be att få stänga av Geography för rapportsviten.

## Dimensionsvärden

Dimensionsvärdena omfattar regioner och landet som regionen finns i. Exempelvärdena inkluderar `"California"`, `"Texas"`eller `"Virginia"`. Dimensionsvärdet `"Unspecified"` omfattar all internationell trafik utanför USA.

## Skillnader mellan rapporterad och faktisk plats

Eftersom den här dimensionen baseras på IP-adress kan vissa scenarier visa en skillnad mellan den rapporterade platsen och den faktiska platsen:

* **IP-adresser som representerar företagsproxies**: Dessa besökare kan visas som trafik som kommer via användarens företagsnätverk, vilket kan vara en annan plats om användaren arbetar fjärranslutet.
* **Mobila IP-adresser**: Målgruppsanpassning för mobil IP fungerar på olika nivåer beroende på plats och nätverk. Ett antal transportföretag backar tillbaka IP-trafik genom centraliserade eller regionala närvaroplatser.
* **Användare** av satelliter: Det är svårt att identifiera den specifika platsen för dessa användare eftersom de vanligtvis verkar komma från platsen för överordnad länk.
* **Militär- och myndighetsutövare**: Representerar personal som reser runt i världen och tar sig in genom sin hemort, i stället för den bas eller det kontor där de för närvarande är stationerade.
