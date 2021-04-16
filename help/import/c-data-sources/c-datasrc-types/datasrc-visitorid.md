---
description: Du kan integrera besökar-ID:n genom att välja kategorin Allmänt (transaktions-ID).
subtopic: Data sources
title: Besökar-ID
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 7%

---

# Besökar-ID

Du kan integrera besökar-ID:n genom att välja kategorin Allmänt (transaktions-ID).

Se [Integrera offlinedata](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

<p class="head"> <b>Dimensioner för besökar-ID</b> </p>

| Kolumnnamn | Beskrivning |
|--- |--- |
| Besökar-ID | (Obligatoriskt) Unikt värde som representerar en kund både online och offline. |
| Datum | Använd följande datumformat:  MM/DD/YYY/hh/mm/ss (t.ex. 07/14/2017/06/00/00) |
| Spårningskod | Namn på spårningskod. |
| Kategori | Kategorinamn.  Om du anger en kategori måste du också välja en produkt. |
| Kanal | Kanalnamn. |
| eVarn | Varnnamn. Giltiga värden för n är heltal 1-75. |
| Produkt | Produktnamn. |
| Läge | Lägesnamn. |
| Postnummer | Postnamn. |

**Mätvärden för besökar-ID**

| Kolumnnamn | Beskrivning |
|--- |--- |
| Klickningar | Antal spårningskodvyer. |
| Cart Adds | Antal kundvagnstillägg. |
| Cart Open | Antal varukorgar som öppnas. |
| Cart Removes | Antal kundvagnsborttagningar. |
| Kundvagnsvisningar | Antal kundvagnsvyer. |
| Utcheckningar | Antal utcheckningar. |
| Händelse n | Antal gånger händelsen n inträffade. Giltiga värden för n är heltal 1-100.  Om du anger en View-händelse måste du även ange motsvarande datamåda (eVar). Om du till exempel inkluderar eVar2-vyer måste du ange ett värde för eVar2. |
| eVarn-vyer | Antal gånger som eVar n visades. Giltiga värden för n är heltal 1-75. |
| Pris | Produktpris. |
| Beställningar | Antal beställningar som gjorts. |
| Produktvisningar | Antal produktvisningar. |
| Kvantitet | Antal sålda enheter. |
