---
description: Filformat som stöds av klassificeringsuppsättningar
title: Filformat för klassificeringsuppsättning
feature: Classifications
source-git-commit: 2d9eb9179ace40a8d333883cea78dd67329078ab
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---

# Filformat för klassificeringsuppsättning

Klassificeringsuppsättningar har stöd för flera filformat för massöverföring av klassificeringsdata. Varje format har specifika krav för slutförda dataöverföringar.

När filen är korrekt formaterad enligt dessa specifikationer kan du överföra den via gränssnittet Klassificeringsuppsättningar eller API:t. Detaljerade överföringsanvisningar:

* **Webbläsaröverföring**: Se [Schema](manage/schema.md)
* **API-överföring**: Se [API för analysklassificeringar](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

Klassificeringsuppsättningar har stöd för följande filformat:

* **JSON**: JavaScript Object Notation-filer med strukturerade data
* **CSV**: Kommaavgränsade värdefiler
* **TSV/TAB**: Tabbseparerade värdefiler

## Allmänna filkrav

Alla filformat måste uppfylla följande krav:

* **Filkodning**: Använd UTF-8 utan byteordningsmärken. Latin1-kodning stöds också.
* **Teckengränser**: Enskilda klassificeringsvärden har en maxgräns på 255 byte.
* **Nyckelkrav**: Nyckelvärden får inte vara tomma eller bara innehålla blanksteg. Om det finns dubblettnycklar används den sista förekomsten.

+++**JSON-formatinformation**

JSON-filformatet följer konventioner för JSON-rader (JSONL). Filen måste innehålla ett JSON-objekt per rad, där varje objekt representerar en enda klassificeringspost.

>[!NOTE]
>
>Trots följande konventioner för JSON-rader använder du filtillägget `.json` för alla överföringar. Användning av tillägget `.jsonl` kan orsaka fel.

### JSON-struktur

Varje JSON-objekt måste innehålla:

* `key` (obligatoriskt): Unik identifierare för klassificeringsposten
* `data` (krävs för uppdateringar): Ett objekt som innehåller klassificeringskolumnnamn och deras värden
* `action` (valfritt): Den åtgärd som ska utföras. Följande värden stöds:
   * `update` (standard)
   * `delete-field`
   * `delete-key`
* `enc` (valfritt): Datakodningsspecifikation. Följande värden stöds:
   * `utf8` eller `UTF8` (standard)
   * `latin1` eller `LATIN1`

Alla JSON-fältnamn (`key`, `data`, `action`, `enc`) är skiftlägeskänsliga och måste skrivas med gemener.

### JSON-exempel

**Grundläggande uppdateringspost:**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**Uppdatering med angiven kodning:**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**Ta bort specifika fält:**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**Ta bort hela nyckeln:**

```json
{"key": "product999", "action": "delete-key"}
```

### JSON-valideringsregler

* Fältet `key` är obligatoriskt och får inte vara null eller tomt.
* För `update`-åtgärder är fältet `data` obligatoriskt och får inte vara tomt.
* För `delete-field`-åtgärder måste fältet `data` innehålla de fält som ska tas bort.
* Fältet `delete-key` får inte finnas för `data`-åtgärder.
* Kodningsvärden som stöds är inte skiftlägeskänsliga och innehåller standardnamn på teckenuppsättningar.

+++

+++**CSV-formatinformation**

CSV-filer (kommaseparerade värden) avgränsar klassificeringsdatafält med kommatecken.

### CSV-struktur

* **Rubrikrad**: Den första raden måste innehålla kolumnrubriker och den första kolumnen måste vara nyckelkolumn. Efterföljande kolumner ska matcha namn i ditt klassificeringsschema
* **Datarader**: Varje efterföljande rad innehåller klassificeringsdata
* **Avgränsare**: Fält avgränsas med kommatecken
* **Citat**: Fält som innehåller kommatecken, citattecken eller radmatningar ska omslutas av citattecken

### CSV-exempel

**Grundläggande klassificeringsdata:**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**Ta bort hela nyckeln:**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**Ta bort specifika fält (blandat med uppdateringar):**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### CSV-formateringsregler

* Fält som innehåller kommatecken måste omslutas av citattecken
* Fält som innehåller dubbla citattecken måste escape-citattecken genom att dubblera dem (`""`)
* Tomma fält representerar null-värden för den klassificeringen
* Radavstånd och avslutande blanksteg runt fält trimmas automatiskt
* Specialtecken (tabbar, nya rader) i citattecken bevaras

**Ta bort åtgärder:**
* Använd `~deletekey~` i alla fält för att ta bort hela nyckeln och alla dess klassificeringsdata
* Använd `~empty~` i specifika fält om du bara vill ta bort dessa klassificeringsvärden (övriga fält förblir oförändrade)
* När du använder `~empty~` kan du blanda borttagningar med uppdateringar i samma fil

+++

+++**Information om TSV-/TAB-format**

I TSV- (Tab-Separated Values) och TABB-filer används tabbtecken för att skilja klassificeringsdatafält åt.

### Struktur för TSV/TAB

* **Rubrikrad**: Den första raden måste innehålla kolumnrubriker och den första kolumnen måste vara nyckelkolumn. Efterföljande kolumner ska matcha namn i ditt klassificeringsschema
* **Datarader**: Varje efterföljande rad innehåller klassificeringsdata
* **Avgränsare**: Fält avgränsas med tabbtecken (`\t`)
* **Citat**: I allmänhet behövs ingen offert, men vissa implementeringar stöder citattecken

### Exempel på TSV/TAB

**Grundläggande klassificeringsdata:**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**Ta bort hela nyckeln:**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**Ta bort specifika fält (blandat med uppdateringar):**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### Formateringsregler för TSV/TAB

* Fält avgränsas med enkla tabbtecken
* Tomma fält (sammanhängande flikar) representerar null-värden
* Normalt krävs ingen specialoffert
* Radavstånd och avslutande blanksteg bevaras
* Radmatningstecken i fält bör undvikas

**Ta bort åtgärder:**
* Använd `~deletekey~` i alla fält för att ta bort hela nyckeln och alla dess klassificeringsdata
* Använd `~empty~` i specifika fält om du bara vill ta bort dessa klassificeringsvärden (övriga fält förblir oförändrade)
* När du använder `~empty~` kan du blanda borttagningar med uppdateringar i samma fil

+++

## Felhantering

Vanliga problem och lösningar vid överföring:

### Allmänna filformatsfel

* **Ogiltigt filformat**: Kontrollera att filtillägget matchar innehållsformatet (.json, .csv, .tsv eller .tab).
* **&quot;Okänt huvud&quot;**: Kolumnnamn måste matcha klassificeringsmängdens schema (gäller för alla format).

### CSV/TSV-specifika fel

* **&quot;Första kolumnen måste vara nyckeln&quot;**: Kontrollera att CSV/TSV-filen har en korrekt rubrikrad med nyckelkolumnen först.
* **&quot;Minst två rubrikobjekt krävs&quot;**: CSV-/TSV-filer måste ha minst en nyckelkolumn och en klassificeringskolumn.
* **&quot;Den första huvudkolumnen måste heta Key&quot;**: Den första kolumnrubriken måste vara exakt Key (versalt K, skiftlägeskänsligt).
* **&quot;Tomma rubriker tillåts inte&quot;**: Alla CSV-/TSV-kolumnrubriker måste ha namn.
* **&quot;Antalet kolumner matchade inte rubrikerna&quot;**: Varje CSV/TSV-datarad måste ha samma antal fält som rubrikraden.
* **&quot;Felaktigt dokument&quot;**: Kontrollera CSV-citering, rätt tabbseparation i TSV-filer osv.

### JSON-specifika fel

* **&quot;Key is a required field&quot;**: All JSON records must have a non-empty `"key"` field (lowercase, case-sensitive).
* **&quot;Data är ett obligatoriskt fält när action=update används&quot;**: JSON-uppdateringsåtgärder måste innehålla ett `"data"`-fält.
* **&quot;Data är ett obligatoriskt fält när åtgärd=delete-field&quot;** används: JSON delete-field-åtgärder måste ange vilka fält som ska tas bort i fältet `"data"`.
* **&quot;Data får inte finnas när action=delete-key&quot;** används: JSON delete-key-åtgärder kan inte innehålla ett `"data"`-fält.
* **&quot;Kodning som inte stöds&quot;**: Använd bara kodningsvärden som stöds i fältet `"enc"` (utf8, UTF8, latin1, LATIN1).
* **Ogiltig JSON-syntax**: Kontrollera att JSON-filen är korrekt formaterad enligt JSONL-konventioner. Kontrollera också om det finns allmän JSON-formatering, saknade citattecken, kommatecken, hakparenteser osv.

### Storleksbegränsningsfel

* **&quot;Nyckeln överskrider maxstorleken&quot;**: Enskilda nycklar får inte överskrida 255 byte.
* **&quot;Kolumnvärdet överskrider maxstorleken&quot;**: Enskilda klassificeringsvärden får inte överskrida 255 byte.

## Bästa praxis

* **Filstorlek**: 50 MB är den maximala filstorleken för webbläsaröverföringar och API-överföringar.
* **Gruppbearbetning**: För stora datauppsättningar bör du dela upp dem i mindre filer.
* **Dataverifiering**: Testa med en liten exempelfil innan du överför stora datamängder.
* **Säkerhetskopiera**: Behåll kopior av dina källdatafiler.
* **Inkrementella uppdateringar**: Använd JSON-format för att få exakt kontroll över uppdateringar och borttagningar av enskilda poster.
