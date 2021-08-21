---
title: getTimeParting
description: Mät tiden då en viss åtgärd utförs.
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '704'
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

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
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

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getTimeParting` använder följande argument:

**`t`** (Valfritt men rekommenderas, sträng): Namnet på den tidszon som besökarens lokala tid ska konverteras till.  Standardvärdet är UTC/GMT-tid. En fullständig lista över giltiga värden finns i [Lista över tidszoner för TZ-databaser](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) på Wikipedia.

Vanliga giltiga värden är:

* `"America/New_York"` för Eastern Time
* `"America/Chicago"` för centraltid
* `"America/Denver"` för Mountain Time
* `"America/Los_Angeles"` för Pacific Time

Anrop till den här funktionen returnerar en sträng som innehåller följande avgränsade med en pipe (`|`):

* Det aktuella året
* Den aktuella månaden
* Dag i månaden
* Veckodagen
* Aktuell tid (AM/PM)

## Exempel

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## Versionshistorik

### 6.3 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

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
