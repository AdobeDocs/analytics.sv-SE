---
description: Förstå de olika filformat som klassificeringsgrupper stöder
title: Filformat för klassificeringsuppsättning
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 0%

---

# Filformat för klassificeringsuppsättning

Klassificeringsuppsättningar har stöd för flera filformat för överföring av klassificeringsdata. Varje format har specifika krav för slutförda dataöverföringar.

När filen är korrekt formaterad enligt dessa specifikationer kan du överföra data via gränssnittet Klassificeringsuppsättningar eller API. Detaljerade överföringsanvisningar:

* **Webbläsaröverföring**: Se [Överför](manage/schema.md#upload) i gränssnittet [Schema](manage/schema.md) för en klassificeringsgrupp.
* **API-överföring**: Se [API för analysklassificeringar](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

Klassificeringsuppsättningar har stöd för följande filformat:

* **JSON**: JavaScript Object Notation-filer med strukturerade data
* **CSV**: Kommaavgränsade värdefiler
* **TSV eller TAB**: Tabbseparerade värdefiler

## Allmänna filkrav

Alla filformat måste uppfylla följande krav:

* **Filkodning**: Använd UTF-8 utan byteordningsmärken. Latin1-kodning stöds också.
* **Teckengränser**: Enskilda klassificeringsvärden har en maxgräns på 255 byte.
* **Nyckelkrav**: Nyckelvärden får inte vara tomma eller bara innehålla blanksteg. Om det finns dubblettnycklar används den sista förekomsten.

+++ JSON-formatinformation

JSON-filformatet följer konventioner för JSON-rader (JSONL). Filen måste innehålla ett JSON-objekt per rad, där varje objekt representerar en enda klassificeringspost.

>[!NOTE]
>
>Trots att du följer konventionerna för JSON-rader använder du filtillägget `.json` för alla överföringar. Användning av tillägget `.jsonl` kan orsaka fel.

### JSON-struktur

Varje JSON-objekt måste innehålla:

* `key` (obligatoriskt): Unik identifierare för klassificeringsposten
* `data` (krävs för uppdateringar): Ett objekt som innehåller klassificeringskolumnnamn och deras värden
* `action` (valfritt): Den åtgärd som ska utföras. Följande värden stöds:
   * `update` (standardåtgärden när ingen åtgärd har angetts)
   * `delete-field`
   * `delete-key`
* `enc` (valfritt): Datakodningsspecifikation. Följande värden stöds:
   * `utf8` eller `UTF8` (standard)
   * `latin1` eller `LATIN1`

Alla JSON-fältnamn (`key`, `data`, `action`, `enc`) är skiftlägeskänsliga och måste skrivas med gemener.

### JSON-valideringsregler

* Fältet `key` är obligatoriskt och får inte vara null eller tomt.
* För `update`-åtgärder är fältet `data` obligatoriskt och får inte vara tomt.
* För `delete-field`-åtgärder måste fältet `data` innehålla de fält som ska tas bort.
* Fältet `delete-key` får inte finnas för `data`-åtgärder.
* Kodningsvärden som stöds är inte skiftlägeskänsliga och innehåller standardnamn på teckenuppsättningar.

### JSON-exempel

Några exempel på JSON-poster i en JSON-fil.

#### Grundläggande uppdateringspost

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

#### Uppdatera med angiven kodning

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

#### Ta bort specifika fält

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

#### Ta bort en hel nyckel

```json
{"key": "product999", "action": "delete-key"}
```


+++

+++ Information om CSV-format

CSV-filer (kommaseparerade värden) avgränsar klassificeringsdatafält med kommatecken.

### CSV-struktur

* **Rubrikrad**: Den första raden måste innehålla kolumnrubriker och den första kolumnen måste vara nyckelkolumn. Efterföljande kolumner ska matcha namn i ditt klassificeringsschema
* **Datarader**: Varje efterföljande rad innehåller klassificeringsdata
* **Avgränsare**: Fält avgränsas med kommatecken
* **Citat**: Fält som innehåller kommatecken, citattecken eller radmatningar ska omslutas av citattecken

### CSV-formateringsregler

* Fält som innehåller kommatecken måste omslutas av citattecken.
* Fält som innehåller dubbla citattecken måste undvika citattecken genom att dubblera dem (`""`).
* Tomma fält representerar null-värden för den klassificeringen.
* Radavstånd och avslutande blanksteg runt fält trimmas automatiskt.
* Specialtecken (tabbar, nya rader) i citattecken bevaras.

### CSV-borttagningsåtgärder

* Använd `~deletekey~` i alla fält för att ta bort hela nyckeln och alla dess klassificeringsdata
* Använd `~empty~` i specifika fält om du bara vill ta bort dessa klassificeringsvärden (övriga fält förblir oförändrade)
* När du använder `~empty~` kan du blanda borttagningar med uppdateringar i samma fil

### CSV-exempel

Några exempel på CSV-poster i en CSV-fil.

#### Grundläggande klassificeringsdata

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

#### Ta bort en hel nyckel

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

#### Ta bort specifika fält (blandat med uppdateringar)

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

+++

+++ Formatinformation för TSV och TAB

I TSV- (Tab-Separated Values) och TABB-filer används tabbtecken för att skilja klassificeringsdatafält åt.

### Strukturen för TSV och TAB

* **Rubrikrad**: Den första raden måste innehålla kolumnrubriker och den första kolumnen måste vara nyckelkolumn. Efterföljande kolumner ska matcha namn i ditt klassificeringsschema.
* **Datarader**: Varje efterföljande rad innehåller klassificeringsdata.
* **Avgränsare**: Fält avgränsas med tabbtecken (`\t`).
* **Citat**: I allmänhet behövs ingen offert, men vissa implementeringar stöder citattecken.

### Formateringsregler för TSV och TAB

* Fält avgränsas med enkla tabbtecken.
* Tomma fält (på varandra följande flikar) representerar null-värden.
* Normalt behövs ingen specialoffert.
* Radavstånd och avslutande blanksteg bevaras.
* Tidslinjetecken i fält bör undvikas.

### Åtgärder för att ta bort TSV och TABB

* Använd `~deletekey~` i vilket fält som helst för att ta bort hela nyckeln och alla dess klassificeringsdata.
* Använd `~empty~` i specifika fält om du bara vill ta bort dessa klassificeringsvärden (lämnar andra fält intakta).
* När du använder `~empty~` kan du blanda borttagningar med uppdateringar i samma fil.

### Exempel på TSV och TAB

Några exempel på TSV- eller TAB-avgränsade poster i en TSV- eller TAB-fil.

#### Grundläggande klassificeringsdata

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

#### Ta bort en hel nyckel

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

#### Ta bort specifika fält (blandat med uppdateringar)

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

+++

## Felhantering

Vanliga problem och lösningar vid överföring av filer:

### Allmänna filformatsfel

* **Ogiltigt filformat**: Verifiera att filtillägget matchar innehållsformatet (`.json`, `.csv`, `.tsv` eller `.tab`).
* **Okänt huvud**: Kolumnnamn måste matcha ditt klassificeringsmängdsschema (gäller för alla format).

### JSON-specifika fel

* **Nyckeln är ett obligatoriskt fält**: Alla JSON-poster måste ha ett `"key"`-fält som inte är tomt (skiftlägeskänsligt).
* **Data är ett obligatoriskt fält när åtgärd=uppdatering** används: JSON-uppdateringsåtgärder måste innehålla ett `"data"`-fält.
* **Data är ett obligatoriskt fält när åtgärd=delete-field** används: JSON delete-field-åtgärder måste ange vilka fält som ska tas bort i fältet `"data"`.
* **Data får inte finnas när action=delete-key** används: JSON delete-key-åtgärder kan inte innehålla ett `"data"`-fält.
* **Kodning som inte stöds**: Använd bara kodningsvärden som stöds i fältet `"enc"` (`utf8`, `UTF8`, `latin1`, `LATIN1`).
* **Ogiltig JSON-syntax**: Kontrollera att JSON-filen är korrekt formaterad enligt JSONL-konventioner. Kontrollera också om det finns allmän JSON-formatering, saknade citattecken, kommatecken, hakparenteser osv.


### CSV- och TSV-specifika fel

* **Den första kolumnen måste vara nyckeln**: Kontrollera att CSV- eller TSV-filen har en korrekt rubrikrad med nyckelkolumnen först.
* **Minst två rubrikobjekt krävs**: CSV- eller TSV-filer måste ha minst en `Key`-kolumn och en klassificeringskolumn.
* **Den första rubrikkolumnen måste heta Key**: Den första kolumnrubriken måste vara exakt `Key` (versalt `K`, skiftlägeskänsligt).
* **Tomma rubriker tillåts inte**: Alla CSV-/TSV-kolumnrubriker måste ha namn.
* **Antalet kolumner matchade inte rubrikerna**: Varje CSV- eller TSV-datarad måste ha samma antal fält som rubrikraden.
* **&quot;Felformaterat dokument**: Kontrollera CSV-citat, rätt tabbseparation i TSV-filer med mera.


### Storleksbegränsningsfel

* **Nyckeln överskrider maxstorleken**: Enskilda nycklar får inte överskrida 255 byte.
* **Kolumnvärdet överskrider maxstorleken**: Enskilda klassificeringsvärden får inte överskrida 255 byte.

## Bästa praxis

* **Filstorlek**: 50 MB är den maximala filstorleken för webbläsaröverföringar och API-överföringar.
* **Gruppbearbetning**: För stora datauppsättningar bör du dela upp dem i mindre filer.
* **Dataverifiering**: Testa med en liten exempelfil innan du överför stora datamängder.
* **Säkerhetskopiera**: Behåll kopior av dina källdatafiler.
* **Inkrementella uppdateringar**: Använd JSON-formatet för att få exakt kontroll över uppdateringar och borttagningar av enskilda poster.
