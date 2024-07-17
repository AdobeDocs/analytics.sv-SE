---
description: I det här avsnittet beskrivs de filer som hittas vid leverans av en datafeed.
keywords: Datafeed;jobb;innehåll;manifest;fil;sökning;träffdata;leveransinnehåll
subtopic: data feeds
title: Innehåll i datafeed - översikt
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---

# Innehåll i datafeed - översikt

I följande avsnitt beskrivs hur du får åtkomst till och förstår de filer som finns i en leverans av en datafeed.

## Få tillgång till innehåll i datafeed

Så här kommer du åt innehållet i en datafeed:

1. Logga in på målwebbplatsen för datafeed.

   Det här är målwebbplatsen som du konfigurerar när du skapar dataflödet, till exempel en Amazon S3- eller Google Cloud Platform-bucket.

1. Hämta den komprimerade datafeeden till din lokala dator.

1. Zippa upp den komprimerade filen med ett program som stöder `.tar.gz` filtillägg.

1. Öppna filen `hit_data.tsv` i kalkylbladet eller det databasprogram du vill använda för att visa rådata för den dagen. —>

## Manifest-fil {#feed-manifest}

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

Vissa feeds har konfigurerats för att ta emot en `.fin`-fil i stället för ett `.txt`-manifest. `.fin` anger att överföringen är slutförd, men att de metadata som den innehåller är i ett äldre format.

## Sök efter filer

Vissa dataflödeskolumner ger ett tal som motsvarar det faktiska värdet. Uppslagsfiler används för att matcha ett tal från en dataflödeskolumn och matcha det med ett faktiskt värde. Om du till exempel anger värdet 497 i träffdatakolumnen `browser` kommer träffen från Microsoft Internet Explorer 8 om du tittar i `browser.tsv`.

Observera att `column_headers.tsv` och `event_list.tsv` är specifika för dataflödet och rapportsviten. Andra filer, som `browser.tsv`, är generiska.

Uppslagsfilerna levereras tillsammans i en komprimerad zip-fil med följande namn:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**: En enda rad som innehåller kolumnrubrikerna för `hit_data.tsv`.
* **`browser.tsv`**: Mappar webbläsarens ID (kolumnen `browser` feed) till webbläsarens egna namn.
* **`browser_type.tsv`**: Mappar webbläsar-ID:t (`browser` feed-kolumnen) till webbläsartypen.
* **`color_depth.tsv`**: Mappar färgdjup-ID:t (feed-kolumnen `color`) till färgdjup.
* **`connection_type.tsv`**: Mappar anslutningstyp-ID:t (feed-kolumnen `connection_type`) till anslutningstypen.
* **`country.tsv`**: Mappar lands-ID (feed-kolumnen `country`) till landsnamnet.
* **`javascript_version.tsv`**: Mappar JavaScript version-ID (feed-kolumnen `javascript`) till JavaScript-versionen.
* **`languages.tsv`**: Mappar språk-ID (feed-kolumnen `language`) till språk.
* **`operating_systems.tsv`**: Mappar operativsystems-ID (feed-kolumnen `os`) till operativsystemets namn.
* **`plugins.tsv`**: Mappar plugin-ID:n (feed-kolumnen `plugin`) till respektive plugin-programnamn.
* **`resolution.tsv`**: Mappar upplösnings-ID (feed-kolumnen `resolution`) till skärmupplösningen.
* **`referrer_type.tsv`**: Mappar referenstyps-ID (feed-kolumnen `ref_type`) till referenstypen.
* **`search_engines.tsv`**: Mappar sökmotor-ID:t (feed-kolumnen `search_engine`) till sökmotornamnet.
* **`event.tsv`**: Mappar varje händelse-ID (feed-kolumnen `event_list`) till dess respektive händelsenamn.

## Träffa datafiler

Träffdata anges i en `hit_data.tsv`-fil. Mängden data i den här filen avgörs av leveransformatet (varje timme eller dag samt en eller flera filer). Den här filen innehåller bara träffdata. Kolumnrubrikerna levereras separat tillsammans med sökfilerna. Varje rad i filen innehåller ett enda serveranrop.

Filer som levereras med Adobe varierar beroende på vilken typ av datafeed du har konfigurerat. Alla filer är kodade med ISO-8859-1.

* `[rsid]` refererar till det rapportpaket-ID som datafeeden kommer från.
* `[index]` används bara i flera filflöden och refererar till rätt ordning för sidnumrerade filer.
* `[YYYY-mm-dd]` refererar till den startdag som dataflödet är avsett för.
* `[HHMMSS]` används endast i timmatningar och refererar till den starttid som datamatningen är avsedd för.
* `[compression_suffix]` refererar till den komprimeringstyp som används. Vanligtvis komprimeras datafeeds till `tar.gz`- eller `zip`-filer.
* `[format_suffix]` refererar till filformatstypen. Vanligtvis är datafeedfilformatet `.tsv`.

### En fil varje dag

När data har samlats in för en dag får du en enda komprimerad datafil och en manifestfil. Datafilen heter:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

När datafilen extraheras innehåller den en enda `hit_data.tsv`-fil med alla data för den dagen samt sökfiler efter eventuella nödvändiga kolumner.

### Flera filer dagligen

När data har samlats in för en dag får du en eller flera komprimerade datafiler och en manifestfil. Datafilen heter:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

När de extraheras innehåller varje datafil en `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` som innehåller ungefär 2 GB okomprimerade data, samt sökfiler efter nödvändiga kolumner.

### En fil varje timme

När data har samlats in under en timme får du en enda komprimerad datafil och en manifestfil. Datafilen heter:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

När datafilen extraheras innehåller den en enda `hit_data.tsv`-fil med alla data för den timmen, samt sökfiler efter eventuella nödvändiga kolumner.

### Varje timme, flera filer

När data har samlats in under en timme får du en eller flera komprimerade datafiler och en manifestfil. Datafilerna har följande namn:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

När de extraheras innehåller varje datafil en enda `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]`-fil som innehåller ungefär 2 GB okomprimerade data samt sökfiler efter eventuella nödvändiga kolumner.

## Datafilens storlek

Storleken på träffdatafilen varierar kraftigt beroende på antalet variabler som används och mängden trafik som skickas till rapportsviten. I genomsnitt är emellertid en datarad ungefär 500 B (komprimerad) eller 2 kB (okomprimerad). Genom att multiplicera detta med antalet serveranrop kan du få en ungefärlig uppskattning av hur stor dataflödesfilen är. När din organisation får dataflödesfiler kan du hitta ett mer korrekt nummer genom att dividera antalet rader i `hit_data.tsv` med dess totala filstorlek.