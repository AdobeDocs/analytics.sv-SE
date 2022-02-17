---
description: Ej klassificerade nycklar grupperas i klassificeringsrapporter som ett enda radobjekt med etiketten Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.
title: Ej klassificerade nycklar
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 2%

---

# Ej klassificerade nycklar

Ej klassificerade nycklar grupperas i klassificeringsrapporter som ett enda radobjekt med etiketten Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.

## Ej klassificerade nycklar {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Ej klassificerade nycklar grupperas i klassificeringsrapporter som en enda radartikel med etiketten *`None`*. Det kan vara praktiskt att byta namn *`None`* till något mer beskrivande.

Anta till exempel att dina spårningskoder innehåller information som anger vilken typ av mobilkampanj spårningskoden är kopplad till. Du använder klassificering (Mobile Campaign Type) för att gruppera dessa spårningskoder i kategorier som Mobile Web, iOS Application, Android Application och så vidare. Vissa kampanjer kanske inte är mobilkampanjer och klassificeras därför inte med en mobilkampanjtyp. Alla icke-klassificerade spårningskoder grupperas under *`None`* i [!UICONTROL Mobile Campaign Type] rapport.

## Byt namn på klassificeringsnyckeln Ingen {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steg som beskriver hur du byter namn på en icke-klassificerad nyckel som visas som *`none`* vid rapportering.

1. Exportera klassificeringar till en lokal fil med hjälp av importeraren.
1. Lägg till en rad i filen och skriv `~none~` i kolumnen Key.
1. På den rad du lade till skriver du det mer beskrivande namnet i respektive klassificeringskolumn(er).

   Om du vill följa exemplet i den här dokumentationen skriver du&quot;icke-mobil kampanj&quot; i en kolumn med namnet [!UICONTROL Mobile Campaign Type].

   Den här posten byter namn *`None`* till *`non-mobile campaign`* i [!UICONTROL Mobile Campaign Type] rapport.

   ![Exempel på en oklassificerad nyckel](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importera data](/help/components/classifications/importer/import-file.md) tillbaka in i systemet.
