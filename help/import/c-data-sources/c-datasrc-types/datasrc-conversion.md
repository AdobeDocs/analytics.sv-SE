---
description: Datakällor har stöd för följande konverteringsdatamått och -mått för datatyper som bearbetas som konvertering.
subtopic: Data sources
title: Konvertering
topic: Developer and implementation
uuid: 5e7907b1-6c9c-4073-876b-410f3a29767d
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---


# Konvertering

Datakällor har stöd för följande konverteringsdatamått och -mått för datatyper som bearbetas som konvertering.

## Konverteringsdimensioner och mått {#section_FA1731B232B246DABEDF5A5D84159084}

Om du anger en View-händelse måste du även ange motsvarande datamått (eVar). Om du till exempel inkluderar vyer av typen eVar2 måste du ange ett värde för eVar2. Antalet anpassade händelser och eVar-vyer som stöds av en rapportsvit är kontraktsberoende och varierar mellan företag.

<p class="head"> <b>Konverteringsdimensioner</b> </p>

| Kolumnnamn | Beskrivning |
|--- |--- |
| Spårningskod | Namn på spårningskod. |
| Datum | Använd följande datumformat:  MM/DD/YYY/HH/mm/SS (t.ex. 01/01/2015/06/00/00) |
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
| Vyer | Antal kundvagnsvyer. |
| Utcheckningar | Antal utcheckningar. |
| Händelse n | Antal gånger händelsen n inträffade. Giltiga värden för n är heltal 1-100.  Om du anger en View-händelse måste du även ange motsvarande datamått (eVar). Om du till exempel inkluderar vyer av typen eVar2 måste du ange ett värde för eVar2. |
| eVarn-vyer | Antal gånger eVar n visades. Giltiga värden för n är heltal 1-250. |
| Pris | Produktpris. |
| Beställningar | Antal beställningar som gjorts. |
| Produktvyer | Antal produktvisningar. |
| Kvantitet | Antal sålda enheter. |
