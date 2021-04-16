---
description: Ej klassificerade nycklar grupperas tillsammans i klassificeringsrapporter som ett enda radobjekt med namnet Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.
subtopic: Classifications
title: Ej klassificerade nycklar
feature: Administratörsverktyg
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 3%

---

# Ej klassificerade nycklar

Ej klassificerade nycklar grupperas tillsammans i klassificeringsrapporter som ett enda radobjekt med namnet Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.

## Ej klassificerade nycklar {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Nycklar som inte är klassificerade grupperas tillsammans i klassificeringsrapporter som ett enda radobjekt med etiketten *`None`*. Det kan vara praktiskt att byta namn på *`None`* till något mer beskrivande.

Anta till exempel att dina spårningskoder innehåller information som anger vilken typ av mobilkampanj som spårningskoden är kopplad till. Du använder klassificering (Mobile Campaign Type) för att gruppera dessa spårningskoder i kategorier som Mobile Web, iOS Application, Android Application och så vidare. Vissa kampanjer kanske inte är mobilkampanjer och klassificeras därför inte med en mobilkampanjtyp. Alla icke-klassificerade spårningskoder grupperas under *`None`* i [!UICONTROL Mobile Campaign Type]-rapporten.

## Byt namn på klassificeringsnyckeln Ingen {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steg som beskriver hur du byter namn på en icke-klassificerad nyckel som visas som *`none`* i rapporter.

1. Exportera klassificeringar till en lokal fil med hjälp av importeraren.
1. Lägg till en rad i filen och skriv [!DNL ~none~] i Key-kolumnen.
1. På den rad du lade till skriver du det mer beskrivande namnet i respektive klassificeringskolumn(er).

   Om du vill följa exemplet i den här dokumentationen kan du skriva&quot;icke-mobil kampanj&quot; i en kolumn med namnet [!UICONTROL Mobile Campaign Name].

   Den här posten byter namn från *`None`* till *`non-mobile campaign`* i [!UICONTROL Mobile Campaign Type]-rapporten.
1. [Importera ](/help/components/classifications/importer/import-file.md) databasen till systemet.
