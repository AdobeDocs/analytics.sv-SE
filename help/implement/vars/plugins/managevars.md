---
title: manageVars
description: Ändra värdena för mer än en Analytics-variabel åt gången.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: manageVars

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `manageVars` plugin-programmet kan du ändra värdena för flera Analytics-variabler samtidigt. Du kan också ange värden som gemener eller ta bort onödiga tecken från flera variabelvärden samtidigt. Adobe rekommenderar att du använder denna plugin om du vill rensa upp värdet för flera variabler samtidigt.

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
   * Åtgärdstyp: Initiera manageVars
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `manageVars`

* **`cb`** (required, string): Namnet på en callback-funktion som plugin-programmet använder för att ändra Analytics-variablerna. Du kan använda en Adobe-funktion som `cleanStr` eller en egen, anpassad funktion.
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
* **`Il`** (valfritt, boolesk): Ange till `false` om du vill *exkludera* listan med variabler som deklarerats i `l` argumentet i stället för att inkludera dem. Standardvärdet är `true`.

Om du anropar den här metoden returneras ingenting. I stället ändras värdena för Analytics-variabler baserat på den önskade callback-funktionen.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.manageVars("lowerCaseVars");
```

...ändrar värdena för alla variablerna som beskrivs ovan till nedsänkta versioner.  Det enda undantaget till detta är händelsvariabeln, som vissa av händelserna (t.ex. scAdd, scCheckout, osv.) är skiftlägeskänsliga och bör inte sänkas

### Exempel 2

Följande kod...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...ger i stort sett exakt samma resultat som det första exemplet eftersom händelsvariabeln inte sänks som standard.

### Exempel 3

Följande kod...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...ändrar (t.ex. gemener) endast värdena för eVar1, eVar2, eVar3 och list2

### Exempel 4

Följande kod...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...kommer att ändra (t.ex. gemener) värdena för alla variablerna som beskrivs ovan EXCEPT för eVar1, eVar2, eVar3 och list2

### Exempel 5

Följande kod...

```js
s.manageVars("cleanStr");
```

...ändrar värdena för alla de variabler som beskrivs ovan, inklusive händelsvariablerna.  Callback-funktionen clearStr gör följande med varje variabels värde:

* Tar bort HTML-kodning
* Tar bort blanksteg som hittats i början och slutet av värdet
* Ersätter inledande och avslutande citattecken (t.ex. &quot;) med ett rakt enkelt citattecken (&#39;)
* Ersätter tabbtecken, radmatningstecken och radmatningstecken med blanksteg
* Ersätter alla dubbla (eller tre, osv.) blanksteg med enkla blanksteg

## Versionshistorik

### 2.1 (14 januari 2019)

* Felkorrigering för Internet Explorer 11-webbläsare.
* Ändringar för `s.cleanStr`, som nu använder den vanliga `cleanStr` funktionen.

### 2.0 (7 maj 2018)

* Point release (inklusive fullständig omanalys/omskrivning av plugin-program)
* En `cleanStr` återanropsfunktion har lagts till
