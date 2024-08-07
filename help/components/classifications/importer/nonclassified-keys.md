---
description: Ej klassificerade nycklar grupperas i klassificeringsrapporter som ett enda radobjekt med etiketten Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.
title: Ej klassificerade nycklar
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---

# Ej klassificerade nycklar

Ej klassificerade nycklar grupperas i klassificeringsrapporter som ett enda radobjekt med etiketten Ingen. Det kan vara praktiskt att ändra namnet till Inget till något mer beskrivande.

## Ej klassificerade nycklar {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Nycklar som inte är klassificerade grupperas i klassificeringsrapporter som ett enskilt radobjekt med etiketten *`None`*. Det kan vara användbart att byta namn på *`None`* till något mer beskrivande.

Anta till exempel att dina spårningskoder innehåller information som anger vilken typ av mobilkampanj spårningskoden är kopplad till. Du använder klassificering (Mobile Campaign Type) för att gruppera dessa spårningskoder i kategorier som Mobile Web, iOS Application, Android Application och så vidare. Vissa kampanjer kanske inte är mobilkampanjer och klassificeras därför inte med en mobilkampanjtyp. Alla icke-klassificerade spårningskoder grupperas under *`None`* i [!UICONTROL Mobile Campaign Type]-rapporten.

## Byt namn på klassificeringsnyckeln Ingen {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Så här byter du namn på en icke-klassificerad nyckel som visas som *`none`* i rapporter:

1. Exportera klassificeringar till en lokal fil med hjälp av importeraren.
1. Lägg till en rad i filen och skriv `~none~` i nyckelkolumnen.
1. På den rad du lade till skriver du det mer beskrivande namnet i respektive klassificeringskolumn(er).

   Om du vill följa exemplet i den här dokumentationen kan du skriva&quot;icke-mobil kampanj&quot; i en kolumn med namnet [!UICONTROL Mobile Campaign Type].

   Den här posten byter namn från *`None`* till *`non-mobile campaign`* i rapporten [!UICONTROL Mobile Campaign Type].

   ![Exempel på en oklassificerad nyckel](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importera data](/help/components/classifications/importer/import-file.md) tillbaka till systemet.
