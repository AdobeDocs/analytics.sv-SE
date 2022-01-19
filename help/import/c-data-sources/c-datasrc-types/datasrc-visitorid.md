---
description: Du kan integrera besökar-ID:n genom att välja kategorin Allmänt (transaktions-ID).
subtopic: Data sources
title: Besökar-ID
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: a7a116ddc9eddc500a52111e9c002bdbee3e4a56
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%

---

# VisitorID

Besökar-ID:n kan integreras genom att välja [!UICONTROL Call Center Data] kategori.

Se [Integrera offlinedata](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## VisitorID-Dimensioner

| Kolumnnamn | Beskrivning |
|--- |--- |
| [!UICONTROL VisitorID] | (Obligatoriskt) Unikt värde som representerar en kund både online och offline. |
| [!UICONTROL Date] | Använd följande datumformat: `MM/DD/YYYY/hh/mm/ss` (t.ex. 07/14/2017/06/00/00) |
| [!UICONTROL Tracking Code] | Namn på spårningskod. |
| [!UICONTROL Category] | Kategorinamn. Om du anger en kategori måste du också välja en produkt. |
| [!UICONTROL Channel] | Kanalnamn. |
| [!UICONTROL eVar]*n* | eVar *n* namn. Giltiga värden för *n* är heltal 1-75. |
| [!UICONTROL Product] | Produktnamn. |
| [!UICONTROL State] | Lägesnamn. |
| [!UICONTROL Zip] | Postnamn. |

## Mätvärden för besökar-ID

| Kolumnnamn | Beskrivning |
| --- | --- |
| [!UICONTROL Clickthroughs] | Antal spårningskodvyer. |
| [!UICONTROL Cart Adds] | Antal kundvagnstillägg. |
| [!UICONTROL Cart Opens] | Antal varukorgar som öppnas. |
| [!UICONTROL Cart Removes] | Antal kundvagnsborttagningar. |
| [!UICONTROL Cart Views] | Antal kundvagnsvyer. |
| [!UICONTROL Checkouts] | Antal utcheckningar. |
| [!UICONTROL Event]*n* | Antal gånger jämna *n* inträffade. Giltiga värden för n är heltal 1-100.  Om du anger en [!UICONTROL View] -händelsen måste du också ange motsvarande datamängd (eVar). Om du till exempel inkluderar eVar2-vyer måste du ange ett värde för eVar2. |
| [!UICONTROL eVar]*n* Vyer | Antal gånger eVar *n* har visats. Giltiga värden för *n* är heltal 1-75. |
| [!UICONTROL Price] | Produktpris. |
| [!UICONTROL Orders] | Antal beställningar som gjorts. |
| [!UICONTROL Product Views] | Antal produktvisningar. |
| [!UICONTROL Quantity] | Antal sålda enheter. |
