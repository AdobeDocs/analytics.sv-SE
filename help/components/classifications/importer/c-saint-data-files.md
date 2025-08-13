---
description: Importören låter dig ladda upp klassificeringsdata gruppvis för att analysera rapporter i en fil. Importen kräver ett specifikt filformat för slutförda dataöverföringar.
title: Klassificeringsdatafiler
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 0%

---

# Klassificeringsdatafiler (äldre)

{{classification-importer-deprecation}}

Importören låter dig ladda upp klassificeringsdata gruppvis för att analysera rapporter i en fil. Importen kräver ett specifikt filformat för slutförda dataöverföringar.

Du kan skapa giltiga datafiler genom att hämta en mallfil som innehåller en filstruktur där du kan klistra in klassificeringsdata. Mer information finns i [Hämta klassificeringsmall](/help/components/classifications/importer/c-download-saint-data.md).

Mer information om teckengränser i klassificeringar finns i [Allmän filstruktur](/help/components/classifications/importer/c-saint-data-files.md).

## Allmän filstruktur

Följande bild är ett exempel på en datafil:

![](assets/completed-saint-file.png)

En datafil måste följa följande strukturregler:

* Klassificeringar kan inte ha värdet 0 (noll).
* Du bör begränsa antalet import- och exportkolumner till 30.
* Överförda filer ska använda UTF-8 utan BOM-teckenkodning.
* Specialtecken som tabbar, radmatningar och citattecken kan bäddas in i en cell förutsatt att filformatet v2.1 har angetts och cellen är korrekt [escape](/help/components/classifications/importer/importer-faq.md). Specialtecken är:

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  Kommatecknet är inte ett specialtecken.

* Klassificeringsnamn får inte innehålla cirkumflex (^) eftersom det här tecknet används för att ange en underklassificering.
* Var försiktig när du använder bindestreck. Om du t.ex. använder ett bindestreck (-) i en social term tolkas bindestrecket som en [!DNL Not]-operator (minustecknet) i Social. Om du till exempel anger *`fragrance-free`* som en term med importen, identifierar Social termen som *`minus`* fri och samlar in inlägg som anger *`fragrance`*, men inte *`free`*.
* Teckengränser används för att klassificera rapportdata. Om du till exempel överför en klassificeringstextfil för produkter ( *`s.products`*) med produktnamn som är längre än 100 tecken (byte) visas inte produkterna i rapporter. Spårningskoder och alla anpassade konverteringsvariabler (eVars) tillåter 255 byte. Denna policy omfattar även kolumnvärden för klassificering och underklassificering, som omfattas av samma gräns på 255 byte.
* Tabbavgränsad datafil (skapa mallfilen med valfritt kalkylbladsprogram eller textredigeringsprogram).
* Antingen ett `.tab`- eller `.txt`-filtillägg.
* Ett nummertecken (#) identifierar raden som en användarkommentar. Adobe ignorerar alla rader som börjar med #.
* Ett dubbelnummertecken följt av SC (`## SC`) identifierar raden som en huvudkommentar för förbearbetning som används av rapportering. Ta inte bort dessa rader.
* Klassificeringsexporter kan ha dubblettnycklar på grund av radmatningstecken i nyckeln. I en FTP- eller webbläsarexport kan detta lösas genom aktivering av offert för FTP-kontot. Då placeras citattecken runt varje tangent med radmatningstecken.
* Cell C1 på importfilens första rad innehåller en versionsidentifierare som bestämmer hur klassificeringar hanterar användningen av citattecken i resten av filen.

   * v2.0 ignorerar citattecken och antar att de alla är en del av de angivna nycklarna och värdena. Tänk dig följande värde: &quot;This is &quot;&quot;some value&quot;&quot;&quot;. v2.0 skulle tolka detta bokstavligen som: &quot;This is &quot;&quot;some value&quot;&quot;&quot;.
   * v2.1 anger att citattecken är en del av filformateringen som används i Excel-filer. v2.1 formaterar alltså exemplet ovan till: This is &quot;some value&quot;.
   * Problem kan uppstå när v2.1 anges i filen, men det som egentligen önskas är v2.0, det vill säga när citattecken används på ett sätt som inte är tillåtet under Excel-formatering. Om du till exempel har ett värde: &quot;VP NO REPS&quot; S/l Dress w/ Overlay. I v2.1 är detta en felaktig formatering (värdet bör omges av inledande och avslutande citattecken och citattecken som är en del av det faktiska värdet bör föregås av citattecken) och klassificeringar fungerar inte längre än denna punkt.
   * Gör något av följande: ändra filformatet till v2.0 genom att ändra sidhuvudet (cell C1) i de filer du överför, ELLER implementera Excel-citat i alla dina filer.

* Den första (icke-kommentarsraden) i datafilen innehåller de kolumnrubriker som används för att identifiera klassificeringsdata i den kolumnen. Importören kräver ett specifikt format för kolumnrubriker. Mer information finns i [Kolumnrubrikformat](/help/components/classifications/importer/c-saint-data-files.md).
* Omedelbart efter rubrikraden i en datafil finns dataraderna. Varje datarad ska innehålla ett datafält för varje kolumnrubrik.
* Datafilen har stöd för följande kontrollkoder, som Adobe använder för att strukturera filen och för att importera klassificeringsdata på rätt sätt:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> KONTROLLKOD </th> 
   <th colname="col2" class="entry"> BESKRIVNING </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Ny rad&gt; </p> </td> 
   <td colname="col2"> <p>Ett nytt radtecken är den enda avgränsare som stöds mellan datarader/poster i datafilen. Normalt behöver du bara infoga dessa tecken när du skriver ett program för att automatiskt generera datafiler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Begär att Adobe automatiskt ska generera ett unikt ID för det här elementet. </p> <p>I kampanjsammanhang instruerar det här kontrollvärdet Adobe att tilldela varje kreativt element en identifierare. Se <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Key </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Anger att datakolumnen representerar det datumintervall som är associerat med objektet. Se <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Datum </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tomt fält </p> </td> 
   <td colname="col2"> <p>Representerar ett NULL-värde för det aktuella fältet. Använd det här alternativet om en viss datakolumn inte gäller för den aktuella posten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER-modifierare </p> </td> 
   <td colname="col2"> <p>Anger att datakolumnen representerar ett <span class="wintitle"> PER Modifier </span>-fält. Se <a href="/help/components/classifications/importer/c-saint-data-files.md"  > PER modifieringsrubrik </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kolumnrubrikformat

>[!NOTE]
>
>Du bör begränsa antalet import- och exportkolumner till 30.

Klassificeringsfiler har stöd för följande kolumnrubriker:

### Nyckel

Varje värde måste vara unikt i hela systemet. Värdet i det här fältet motsvarar ett värde som tilldelats variabeln [!DNL Analytics] i beacon för din webbplats [!DNL JavaScript]. Data i den här kolumnen kan innehålla ~autogen~ eller någon annan unik spårningskod.

### Klassificeringskolumnrubrik

>[!NOTE]
>
>Värdena i kolumnrubriken [!UICONTROL Classifications] måste exakt matcha klassificeringens namnkonvention, annars misslyckas importen. Om administratören till exempel ändrar [!UICONTROL Campaigns] till [!UICONTROL Internal Campaign Names] i [!UICONTROL Campaign Set-up Manager] måste filkolumnrubriken ändras så att den matchar. &quot;Key&quot; är ett reserverat klassificeringsvärde (header). Nya klassificeringar med namnet Key stöds inte.

Dessutom stöder datafilen följande ytterligare rubriktexter för att identifiera underklassificeringar och andra specialiserade datakolumner:

### Underklassificeringsrubrik

`Campaigns^Owner` är till exempel en kolumnrubrik för kolumnen som innehåller `Campaign Owner` värden. På samma sätt är `Creative Elements^Size` en kolumnrubrik för kolumnen som innehåller underklassificeringen `Size` för klassificeringen `Creative Elements`.

## Felsöka klassificeringar

* [Vanliga problem vid överföring](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): Kunskapsbasartikeln som beskriver problem som uppstår med felaktiga filformat och filinnehåll.
