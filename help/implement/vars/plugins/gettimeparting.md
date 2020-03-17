---
title: getTimeParting
description: Mät tiden då en viss åtgärd utförs.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getTimeParting

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getTimeParting` plugin-programmet kan du hämta information om när mätbara aktiviteter äger rum på webbplatsen. Denna plugin är värdefull när du vill att mätvärden ska delas upp efter en upprepningsbar uppdelning av tiden i ett visst datumintervall. Du kan till exempel jämföra konverteringsgraden mellan två olika veckodagar, till exempel alla söndagar jämfört med alla torsdagar. Du kan också jämföra tidsperioder på dagen, t.ex. alla tider jämfört med alla kvällar.

Analysis Workspace har liknande färdiga dimensioner som formateras något annorlunda än denna plugin. Mer information finns i [Tidsdelningsdimensioner](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) i användarhandboken för Analysera. Vissa organisationer tycker att analysarbetsytans färdiga dimensioner är tillräckliga.

> [VIKTIGT] version 4.0+ av denna plug-in skiljer sig avsevärt från tidigare versioner. Adobe rekommenderar att du implementerar denna plugin från grunden. Kod som refererar till plugin-programmet före version 4.0 är inte kompatibel med den aktuella versionen av det här plugin-programmet.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe erbjuder ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installera och publicera [!UICONTROL Common Analytics Plugins] tillägget
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getTimeParting
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken så att [!UICONTROL Configure tracking using custom code] den visar [!UICONTROL Open Editor] knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med `s_gi`). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getTimeParting`

**`t`** (Valfritt men rekommenderas, sträng): Namnet på den tidszon som besökarens lokala tid ska konverteras till.  Standardvärdet är UTC/GMT-tid. En fullständig lista över giltiga värden finns i [List of TZ database time zone](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) on Wikipedia.

Vanliga giltiga värden är:

* `"America/New_York"` för Eastern Time
* `"America/Chicago"` för centraltid
* `"America/Denver"` för Mountain Time
* `"America/Los_Angeles"` för Pacific Time

Anrop till den här metoden returnerar en sträng som innehåller följande avgränsade med en pipe (`|`):

* Det aktuella året
* Den aktuella månaden
* Dag i månaden
* Veckodagen
* Aktuell tid (AM/PM)

## Exempelanrop

### Exempel på specifika tidszoner

Använd följande exempelkod om klienten är i Paris, Frankrike:

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Om kunden är i San Jose i Kalifornien:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Om kunden befinner sig i det afrikanska landet Ghana:

```js
s.eVarX = getTimeParting();
```

Ghana ligger inom tidzonen UTC/GMT.  I det här exemplet visas att inga plug-in-argument behövs under sådana omständigheter.

### Redovisning för Internet Explorer-webbläsare

Använd följande exempel om du vill exkludera tidsdelade data från Internet Explorer-besökare (eftersom det värde som returneras från IE-webbläsare bara kan finnas i besökarens lokala tid)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultat från samtal

Om en besökare från Denver besöker Colorado en webbplats den 31 augusti 2020 kl. 9.15,

Kör följande kod..

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...skulle ange s.eVar10 som lika med &quot;year=2020| month=August| date=31| day=Friday| time=6:15 PM&quot;

När följande kod..

```js
s.eVar10 = getTimeParting("America/Nome");
```

...skulle ange s.eVar10 som lika med &quot;year=2020| month=August| date=31| day=Friday| time=6:15&quot;

Följande kod...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...skulle ange s.eVar10 som lika med &quot;year=2020| month=August| date=31| day=Friday| time=8:45 PM&quot;

Och följande kod..

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...skulle ange s.eVar10 som lika med &quot;year=2020| month=September| date=1| day=Saturday| time=1:15&quot;

## Versionshistorik

### 6.2 (5 november 2019)

* Små felkorrigeringar
* Minskad total kodstorlek

### 6.1 (26 november 2018)

* Korrigera för Internet Explorer-webbläsare. De kan returnera tiden, men bara på besökarens lokala tid.

### 6.0 (14 augusti 2018)

* Fullständig omskrivning enligt internationella standarder. Nu konverteras sommartid och alla tidszoner korrekt.

### 5.0 (17 april 2018)

* Point Release (omkompilerad, mindre kodstorlek)
* Behovet av `tpDST` parametern har tagits bort eftersom start- och slutdatum för sommartid nu identifieras automatiskt

### 4.0 (22 augusti 2016)

* Tillhandahåller en helt ny lösning och innehåller nu information om år, månad och datum.
