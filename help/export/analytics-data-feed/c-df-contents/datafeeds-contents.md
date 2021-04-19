---
description: I det här avsnittet beskrivs de filer som hittas vid leverans av en datafeed.
keywords: Datafeed;jobb;innehåll;manifest;fil;sökning;träffdata;leveransinnehåll
subtopic: data feeds
title: Innehåll i datafeed - översikt
feature: Rapporter och analyser - Grunderna och analyser
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---

# Innehåll i datafeed - översikt

I det här avsnittet beskrivs de filer som hittas vid leverans av en datafeed.

## Manifest-fil

Manifestfilen innehåller följande information om varje fil som ingår i den överförda datauppsättningen:

* Filnamn
* Filstorlek
* MD5-hash
* Antal poster i filen

Manifestfilen har samma format som Java JAR-manifestfilen.

Manifestfilen levereras alltid sist som en separat `.txt`-fil, så att dess existens indikerar att hela datauppsättningen för den perioden redan har levererats. Manifestfilerna namnges enligt följande:

```text
[rsid]_[YYYY-mm-dd].txt
```

En typisk manifestfil innehåller data som liknar följande:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Varje manifestfil innehåller en rubrik som anger det totala antalet sökfiler, datafiler och det totala antalet poster i alla datafiler. Rubriken följs av flera avsnitt som innehåller information för varje fil som ingår i leveransen av dataflödet.

Vissa feeds är konfigurerade att ta emot en `.fin`-fil i stället för ett `.txt`-manifest. `.fin` anger att överföringen är slutförd, men den innehåller inga metadata om överföringen.

## Sök efter filer

Vissa dataflödeskolumner ger ett tal som motsvarar det faktiska värdet. Uppslagsfiler används för att matcha ett tal från en dataflödeskolumn och matcha det med ett faktiskt värde. Om du till exempel anger värdet &quot;497&quot; i `browser`-träffdatakolumnen kommer träffen från &quot;Microsoft Internet Explorer 8&quot; om du tittar i `browser.tsv`.

Observera att `column_headers.tsv` och `event_list.tsv` är specifika för datafeeden och rapportsviten. Andra filer, till exempel `browser.tsv`, är generiska.

Uppslagsfilerna levereras tillsammans i en komprimerad zip-fil med följande namn:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* [!DNL column_headers.tsv] (anpassat för denna datafeed)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (anpassat för denna datafeed)

## Träffa datafiler

Träffdata anges i en [!DNL hit_data.tsv]-fil. Mängden data i den här filen avgörs av leveransformatet (varje timme eller dag samt en eller flera filer). Den här filen innehåller bara träffdata. Kolumnrubrikerna levereras separat tillsammans med sökfilerna. Varje rad i den här filen innehåller ett enda serveranrop.

Filer som levereras med Adobe varierar beroende på vilken typ av datafeed du har konfigurerat. Alla filer är kodade med ISO-8859-1.

* `[rsid]` refererar till det rapportpaket-ID som dataflödet kommer från.
* `[index]` används endast i flera filflöden och refererar till rätt ordning för sidnumrerade filer.
* `[YYYY-mm-dd]` avser den första dag som dataflödet är avsett för.
* `[HHMMSS]` används endast i timmatningar och avser den starttid som datamatningen är avsedd för.
* `[compression_suffix]` avser den komprimeringstyp som används. Vanligtvis komprimeras dataflöden till `tar.gz`- eller `zip`-filer.

### En fil varje dag

När data har samlats in för en dag får du en enda komprimerad datafil och en manifestfil. Datafilen heter:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

När datafilen extraheras innehåller den en enda `hit_data.tsv`-fil med alla data för den dagen samt sökfiler efter eventuella nödvändiga kolumner.

### Flera filer dagligen

När data har samlats in för en dag får du en eller flera komprimerade datafiler och en manifestfil. Datafilen heter:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

När de extraheras innehåller varje datafil en enda `hit_data.tsv` som innehåller ungefär 2 GB okomprimerade data samt sökfiler efter eventuella nödvändiga kolumner.

### En fil varje timme

När data har samlats in under en timme får du en enda komprimerad datafil och en manifestfil. Datafilen heter:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

När datafilen extraheras innehåller den en enda `hit_data.tsv`-fil med alla data för den timmen, samt sökfiler efter eventuella nödvändiga kolumner.

### Varje timme, flera filer

När data har samlats in under en timme får du en eller flera komprimerade datafiler och en manifestfil. Datafilen heter:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

När de extraheras innehåller varje datafil en enda `hit_data.tsv` som innehåller ungefär 2 GB okomprimerade data samt sökfiler efter eventuella nödvändiga kolumner.

## Datafilens storlek

Storleken på träffdatafilen varierar kraftigt beroende på antalet variabler som används och mängden trafik som skickas till rapportsviten. I genomsnitt är emellertid en datarad ungefär 500 B (komprimerad) eller 2 kB (okomprimerad). Genom att multiplicera detta med antalet serveranrop kan du få en ungefärlig uppskattning av hur stor dataflödesfilen är. När din organisation får dataflödesfiler kan du hitta ett mer korrekt nummer genom att dividera antalet rader i `hit_data.tsv` med den totala filstorleken.
