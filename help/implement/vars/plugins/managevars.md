---
title: manageVars
description: Ändra värdena för mer än en Analytics-variabel åt gången.
feature: Variables
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 0%

---

# Adobe plug-in: manageVars

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

The `manageVars` Med plugin-programmet kan du ändra värdena för flera Analytics-variabler samtidigt. Du kan också ange värden som gemener eller ta bort onödiga tecken från flera variabelvärden samtidigt. Adobe rekommenderar att du använder denna plugin om du vill rensa upp värdet för flera variabler samtidigt.

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera manageVars
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `manageVars` funktionen använder följande argument:

* **`cb`** (required, string): Namnet på en callback-funktion som plugin-programmet använder för att ändra Analytics-variablerna. Du kan använda en Adobe-funktion som `cleanStr` eller en egen funktion.
* **`l`** (valfri, sträng): En kommaavgränsad lista med Analytics-variabler som du vill ändra. Standardvärdet är ALLA Adobe Analytics-variabler när de inte anges, vilket inkluderar:
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * Alla utkast
   * Alla eVars
   * Alla hierarkivariabler
   * Alla listvariabler
   * Alla kontextdatavariabler
* **`Il`** (valfritt, boolesk): Ange till `false` om du vill *exclude* förteckningen över variabler som deklarerats i `l` i stället för att ta med dem. Standardvärdet är `true`.

Anrop till den här funktionen returnerar ingenting. I stället ändras värdena för Analytics-variabler baserat på den önskade callback-funktionen.

## Exempelanrop

### Exempel 1

Följande kod...

```js
manageVars("lowerCaseVars");
```

...ändrar värdena för alla variablerna som beskrivs ovan till nedsänkta versioner.  Det enda undantaget till detta är händelsvariabeln, som vissa av händelserna (t.ex. scAdd, scCheckout, osv.) är skiftlägeskänsliga och bör inte sänkas

### Exempel 2

Följande kod...

```js
manageVars("lowerCaseVars", "events", false);
```

...ger i stort sett exakt samma resultat som det första exemplet eftersom händelsvariabeln inte sänks som standard.

### Exempel 3

Följande kod...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...ändrar (t.ex. gemener) endast värdena för eVar1, eVar2, eVar3 och list2

### Exempel 4

Följande kod...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...kommer att ändra (t.ex. gemener) värdena för alla variabler som beskrivs ovan, EXCEPT för eVar1, eVar2, eVar3 och list2

### Exempel 5

Följande kod...

```js
manageVars("cleanStr");
```

...ändrar värdena för alla de variabler som beskrivs ovan, inklusive händelsvariablerna.  Callback-funktionen clearStr gör följande med varje variabels värde:

* Tar bort kodningen HTML
* Tar bort blanksteg som hittats i början och slutet av värdet
* Ersätter inledande och avslutande citattecken (t.ex. &quot;) med ett rakt enkelt citattecken (&#39;)
* Ersätter tabbtecken, radmatningstecken och radmatningstecken med blanksteg
* Ersätter alla dubbla (eller tre, osv.) blanksteg med enkla blanksteg

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (14 januari 2019)

* Felkorrigering för Internet Explorer 11-webbläsare.
* Ändringar för `s.cleanStr`, som nu använder `cleanStr` funktion.

### 2.0 (7 maj 2018)

* Point release (inklusive fullständig omanalys/omskrivning av plugin-program)
* Tillagd `cleanStr` callback-funktion
