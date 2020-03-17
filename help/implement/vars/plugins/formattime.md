---
title: formatTime
description: Konvertera ett antal sekunder till motsvarande antal minuter, timmar osv.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: formatTime

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `formatTime` plugin-programmet kan du ta valfritt antal sekunder och presentera dem i ett paketerat format, avrundat till ett önskat referensvärde. Adobe rekommenderar att du använder denna plugin om du vill hämta ett tidsvärde i sekunder och konvertera det till ett bucket-format (till exempel minuter, dagar eller veckor). Detta plugin-program behövs inte om du inte vill bucket med sekundbaserade värden i ett tidsrundat format.

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
   * Åtgärdstyp: Initiera formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `formatTime`

* **`ns`** (obligatoriskt, heltal): Antal sekunder att konvertera eller formatera
* **`tf`** (valfri, sträng): Den typ av format som sekunder ska returneras i; standard är sekunder
   * Ange till `"d"` om du vill ha tiden i dagar (avrundat till närmaste 1/4-dagars test som standard)
   * Ange till `"h"` om du vill ha tiden i timmar (avrundat till närmaste 1/4-timmars riktmärke som standard)
   * Ange till `"m"` om du vill ha tiden i minuter (avrundat till närmaste 1/2-minuters test som standard)
   * Ange till `"s"` om du vill ha tiden i sekunder (avrundat till närmaste 5 sekunder som standard)
* **`bml`** (valfritt, tal): Längden på avrundningsriktmärkena. Standardvärdet är de riktmärken som anges i `tf` argumentet

Metoden returnerar antalet sekunder som formaterats med den enhet som du anger i `tf` argumentet. Om `tf` argumentet inte är inställt:

* Allt som är mindre än en minut avrundas till närmaste 5-sekunders test
* Allt mellan en minut och en timme avrundas till närmaste 1/2-minuters test
* Allt som är mellan en timme och en dag avrundas till närmaste kvart-timmars riktmärke
* Allt som är större än en dag avrundas till närmaste dagtest

## Exempel

### Exempel 1

Följande kod...

```js
s.eVar1 = s.formatTime(38242);
```

...ställs in s.eVar1 lika med &quot;10,5 timmar&quot;

Argumentet som skickades - 38 242 sekunder - är lika med 10 timmar, 37 minuter och 22 sekunder.  Eftersom tf-argumentet inte anges i det här anropet och antalet sekunder som skickas är mellan en timme och en dag, kommer plugin-programmet att returnera antalet sekunder som konverterats till närmaste kvarts-test.

### Exempel 2

Följande kod...

```js
s.eVar1 = s.formatTime(38250);
```

...anger s.eVar1 som lika med &quot;10,75 timmar&quot; Argumentet som skickas in - 38 250 sekunder - är lika med 10 timmar, 37 minuter och 30 sekunder.  Genom att avrunda antalet sekunder som skickas in till det närmaste kvart-timmars-riktvärdet i detta fall kommer det slutliga värdet att anges till 10,75 timmar

### Exempel 3

Följande kod...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...ställs in s.eVar1 lika med &quot;637.5 minuter&quot;

I det här fallet tvingar argumentet &quot;m&quot; plugin-programmet att konvertera sekunder till närmaste halvminuters test

### Exempel 4

Följande kod...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...ställs in s.eVar1 lika med &quot;640 minuter&quot;

Värdet för tf-argumentet (&quot;m&quot;) tvingar plugin-programmet att konvertera sekunder till minuter, men värdet för bml-argumentet (20) tvingar också plugin-programmet att avrunda minutkonverteringen till närmaste 20-minutersprenumeration.

### Exempel 5

Följande kod...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...ställs in s.eVar1 som lika med &quot;126 sekunder&quot;, vilket är det närmaste 2-sekundersreferensen till 125 sekunder

### Exempel 6

Följande kod...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...anges som s.eVar1 lika med &quot;3 minuter&quot;, vilket är det närmaste 3-minuterstestet till 125 sekunder

### Exempel 7

Följande kod...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...anges som s.eVar1 lika med &quot;2,4 minuter&quot;, vilket är det närmaste 2/5 minuter långa riktmärket (t.ex. .4 = 2/5) till 145 sekunder

## Versionshistorik

### 1.1 (21 maj 2018)

* Argumentet har lagts till för att ge större flexibilitet vid avrundning `bml`

### 1.0 (15 april 2018)

* Inledande version.
