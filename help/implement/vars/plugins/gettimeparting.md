---
title: getTimeParting
description: Mät tiden då en viss åtgärd utförs.
translation-type: tm+mt
source-git-commit: 01dce7813d60801f5c7826a903bb97d0db5d2617
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---


# Adobe plug-in: getTimeParting

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getTimeParting` kan du samla in information om när mätbara aktiviteter äger rum på din plats. Denna plugin är värdefull när du vill att mätvärden ska delas upp efter en upprepningsbar uppdelning av tiden i ett visst datumintervall. Du kan till exempel jämföra konverteringsgraden mellan två olika veckodagar, till exempel alla söndagar jämfört med alla torsdagar. Du kan också jämföra tidsperioder på dagen, t.ex. alla tider jämfört med alla kvällar.

Analysis Workspace har liknande färdiga dimensioner som formateras något annorlunda än denna plugin. Mer information finns i [Tidsdelningsdimensioner](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) i användarhandboken för Analysera. Vissa organisationer tycker att Analysis Workspace färdiga dimensioner är tillräckliga.

>[!IMPORTANT]
>
>Version 4.0+ av denna plug-in skiljer sig avsevärt från tidigare versioner. Adobe rekommenderar att du implementerar det här plugin-programmet från grunden. Kod som refererar till plugin-programmet före version 4.0 är inte kompatibel med den aktuella versionen av det här plugin-programmet.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getTimeParting
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getTimeParting` använder följande argument:

**`t`** (Valfritt men rekommenderas, sträng): Namnet på den tidszon som besökarens lokala tid ska konverteras till.  Standardvärdet är UTC/GMT-tid. En fullständig lista över giltiga värden finns i [Lista över tidszoner för TZ-databaser](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) på Wikipedia.

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

Ghana ligger inom tidzonen UTC/GMT. I det här exemplet visas att inget plug-in-argument krävs för UTC/GMT.

### Redovisning för Internet Explorer-webbläsare

Använd följande exempel om du vill exkludera tidsåtgången för att dela data från Internet Explorer-besökare. Värdet som returneras från IE-webbläsare finns bara i besökarens lokala tid.

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultat från samtal

Tänk dig ett scenario där en besökare från Denver Colorado besöker en webbplats den 31 augusti 2020 kl. 9.15.

```js
s.eVar10 = getTimeParting("Europe/Athens");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

s.eVar11 = getTimeParting("America/Nome");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

s.eVar12 = getTimeParting("Asia/Calcutta");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

s.eVar13 = getTimeParting("Australia/Sydney");
// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
```

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
* Behovet av parametern `tpDST` har tagits bort eftersom start-/slutdatum för sommartid nu identifieras automatiskt

>[!CAUTION]
>
>Tidigare versioner av denna plugin kunde inte användas för alla år i framtiden. Om du använder en tidigare version av detta plugin-program rekommenderar Adobe starkt att du uppgraderar till den senaste versionen för att undvika JavaScript-fel och dataförluster. Om det inte går att uppgradera det här plugin-programmet kontrollerar du att variabeln `s._tpdst` i plugin-programkoden innehåller rätt år i framtiden.

### 4.0 (22 augusti 2016)

* Tillhandahåller en helt ny lösning och innehåller nu information om år, månad och datum.
