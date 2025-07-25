---
title: manageVars
description: Ändra värdena för mer än en Analytics-variabel åt gången.
feature: Appmeasurement Implementation
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# Adobe plug-in: manageVars

{{plug-in}}

Med plugin-programmet `manageVars` kan du ändra värdena för flera Analytics-variabler samtidigt. Du kan också ange värden som gemener eller ta bort onödiga tecken från flera variabelvärden samtidigt. Adobe rekommenderar att du använder denna plugin om du vill rensa upp värdet för flera variabler samtidigt.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Inget
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för gemensam analys
   * Åtgärdstyp: Initiera manageVars
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken [!UICONTROL Configure tracking using custom code] som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `manageVars` använder följande argument:

* **`cb`** (required, string): Namnet på en callback-funktion som plugin-programmet använder för att ändra Analytics-variablerna. Du kan använda en Adobe-funktion som `cleanStr` eller en egen anpassad funktion.
* **`l`** (valfritt, sträng): En kommaavgränsad lista med Analytics-variabler som du vill ändra. Standardvärdet är ALLA Adobe Analytics-variabler när de inte är inställda, vilket inkluderar:
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
* **`Il`** (valfritt, booleskt): Ange till `false` om du vill *exkludera* listan med variabler som deklarerats i argumentet `l` i stället för att inkludera dem. Standardvärdet är `true`.

Anrop till den här funktionen returnerar ingenting. I stället ändras värdena för Analytics-variabler baserat på den önskade callback-funktionen.

## Exempelanrop

### Exempel 1

Följande kod...

```js
manageVars("lowerCaseVars");
```

...ändrar värdena för alla variablerna som beskrivs ovan till nedsänkta versioner.  Det enda undantaget till detta är variabeln events, eftersom vissa händelser (t.ex. scAdd, scCheckout, osv.) är skiftlägeskänsliga och inte bör sänkas

### Exempel 2

Följande kod...

```js
manageVars("lowerCaseVars", "events", false);
```

...ger i stort sett exakt samma resultat som det första exemplet eftersom variabeln events inte sänks som standard.

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

... kommer att ändra (t.ex. gemener) värdena för alla variablerna som beskrivs ovan EXCEPT för eVar1, eVar2, eVar3 och list2

### Exempel 5

Följande kod...

```js
manageVars("cleanStr");
```

...ändrar värdena för alla de variabler som beskrivs ovan, inklusive händelsevariablerna.  Callback-funktionen clearStr gör följande med varje variabels värde:

* Tar bort HTML-kodning
* Tar bort blanksteg som hittats i början och slutet av värdet
* Ersätter vänster/höger enkla citattecken med ett rakt enkelt citattecken (`'`)
* Ersätter tabbtecken, radmatningstecken och radmatningstecken med blanksteg
* Ersätter alla dubbla (eller tredubbla, osv.) blanksteg med enkla blanksteg

## Tidigare versioner

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (14 januari 2019)

* Felkorrigering för Internet Explorer 11-webbläsare.
* Ändringar för `s.cleanStr`, som nu använder den vanliga `cleanStr`-funktionen.

### 2.0 (7 maj 2018)

* Point-release (inklusive fullständig omanalys/omskrivning av plugin-program)
* `cleanStr` återanropsfunktion har lagts till
