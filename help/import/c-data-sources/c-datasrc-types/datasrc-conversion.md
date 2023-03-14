---
description: Datakällor har stöd för följande konverteringsdatamått och -mått för datatyper som bearbetas som konvertering.
subtopic: Data sources
title: Konvertering
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 00450ad4-7148-4cf1-bdba-5d1732dd0fd3
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Konvertering

Datakällor har stöd för följande konverteringsdatamått och -mått för datatyper som bearbetas som konvertering.

## Dimensioner och mått för konvertering {#section_FA1731B232B246DABEDF5A5D84159084}

Om du anger en View-händelse måste du även ange motsvarande datamåda (eVar). Om du till exempel inkluderar eVar2-vyer måste du ange ett värde för eVar2. Antalet anpassade händelser och eVar som stöds av en rapportserie är kontraktsberoende och varierar mellan företag.

<p class="head"> <b>Konverteringsdimensioner</b> </p>

| Kolumnnamn | Beskrivning |
|--- |--- |
| Spårningskod | Namn på spårningskod. |
| Datum | Använd följande datumformat: MM/DD/YYY/HH/mm/SS (t.ex. 01/01/2015/06/00/00) |
| Kategori | Kategorinamn.  Om du anger en kategori måste du också välja en produkt. |
| Kanal | Kanalnamn. |
| eVarn | Varnnamn. Giltiga värden för n är heltal 1-250. |
| Produkt | Produktnamn. |
| Läge | Lägesnamn. |
| Postnummer | Postnamn. |

<p class="head"> <b>Konverteringsmått</b> </p>

| Kolumnnamn | Beskrivning |
|--- |--- |
| Klickningar | Antal spårningskodvyer. |
| Cart Adds | Antal kundvagnstillägg. |
| Cart Open | Antal varukorgar som öppnas. |
| Cart Removes | Antal kundvagnsborttagningar. |
| Kundvagnsvisningar | Antal kundvagnsvyer. |
| Utcheckningar | Antal utcheckningar. |
| Händelse n | Antal gånger händelsen n inträffade. Giltiga värden för n är heltal 1-100.  Om du anger en View-händelse måste du även ange motsvarande datamåda (eVar). Om du till exempel inkluderar eVar2-vyer måste du ange ett värde för eVar2. |
| eVarn-vyer | Antal gånger som eVar n visades. Giltiga värden för n är heltal 1-250. |
| Pris | Produktpris. |
| Beställningar | Antal beställningar som gjorts. |
| Produktvisningar | Antal produktvisningar. |
| Kvantitet | Antal sålda enheter. |
