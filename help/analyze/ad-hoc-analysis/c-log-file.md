---
title: Loggfil
description: Hämta en loggfil för felsökning.
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 2%

---


# Loggfil

>[!IMPORTANT]
>
>Adobe flyttar Ad Hoc Analysis till livscykelns slutstatus den 1 mars 2021. [Läs mer...](https://adobe.ly/discoverworkspace).

När du felsöker problem med Ad Hoc Analysis är det ibland nödvändigt att hämta loggfilen. Adobe kan använda loggfilen för att hitta orsaken till problemet och ge en lösning. Filen `discover.log` innehåller alla användarinteraktioner, rapportinläsningsinformation och Java-felmeddelanden för alla sessioner. Den kraschar all skyddad information, t.ex. användarens lösenord. Stora loggfiler delas upp i steg om 10 MB. När du förser Adobe med loggfilerna måste du se till att alla filer är markerade.

## Windows

Hämta `discover.log` filen för Windows:

1. Klicka på Start-menyn och välj **Kör** eller tryck på `[Win]` + `[R]`.
2. Klistra in följande i textfältet och klicka på **OK**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Markera alla filer i mappen, högerklicka och välj **Skicka till > Komprimerad mapp**.
4. Ange ZIP-filen till Adobe-representanten.

## Mac

Så här hämtar du `discover.log` filen för Mac OS:

1. Öppna Finder och gå till `/Users/your-user/.adobe/Discover/log`
2. Markera alla filer i mappen, högerklicka och välj **Komprimera**.
3. Ange ZIP-filen till Adobe-representanten.

Om den totala storleken för komprimerade filer överstiger 10 MB kan en Adobe-representant ange en tillfällig FTP-plats.
