---
title: getNewRepeat
description: Spåra aktiviteter för nya eller återkommande besökare.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getNewRepeat

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getNewRepeat` plugin-programmet kan du avgöra om en besökare på webbplatsen är en ny besökare eller en återkommande besökare inom ett visst antal dagar. Adobe rekommenderar att du använder denna plugin om du vill identifiera besökare som&quot;nya&quot; med ett anpassat antal dagar. Denna plugin behövs inte om dimensionerna Ny/Upprepa besökare i Analysis Workspace uppfyller organisationens behov.

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
   * Åtgärdstyp: Initiera getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getNewRepeat`

* **`d`** (heltal, valfritt): Minsta antal dagar mellan besöken som återställer besökarna till `"New"`. Om argumentet inte är inställt är det som standard 30 dagar.

Den här metoden returnerar värdet för `"New"` om den cookie som angetts av plugin-programmet inte finns eller har upphört att gälla. Det returnerar värdet för `"Repeat"` om den cookie som angetts av plugin-programmet finns och tiden sedan den aktuella träffen och tiden som angetts i cookien är längre än 30 minuter. Den här metoden returnerar samma värde för ett helt besök.

Denna plugin använder en cookie med namnet `"s_nr[LENGTH]"` där `[LENGTH]` är lika med `d` argumentet. Cookien innehåller en Unix-tidsstämpel som representerar den aktuella tiden och besökarens aktuella status (`"New"` eller `"Repeat"`).

## Exempelanrop

### Exempel 1

Följande kod ställer in s.eVar1 lika med värdet &quot;New&quot; för nya besökare och fortsätter att ställa in s.eVar1 lika med värdet &quot;New&quot; (för varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1=s.getNewRepeat();
```

### Exempel 2

Om besökaren kommer tillbaka till webbplatsen när som helst mellan 31 minuter och 30 dagar sedan den senaste gången s.getNewRepeat() anropades, kommer följande kod att ange s.eVar1 som lika med värdet för &quot;Repeat&quot; och kommer att fortsätta att ange s.eVar1 som lika med värdet för &quot;Repeat&quot; (med varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1=s.getNewRepeat();
```

### Exempel 3

Om besökaren inte har varit på webbplatsen på minst 30 dagar sedan den senaste gången s.getNewRepeat() anropades, kommer följande kod att anges som s.eVar1 lika med värdet &quot;New&quot; och kommer att fortsätta att anges som s.eVar1 lika med värdet &quot;New&quot; (med varje nytt anrop) under resten av besökarens besök på webbplatsen.

```js
s.eVar1=s.getNewRepeat();
```

### Exempel 4

Om besökaren kommer tillbaka till webbplatsen när som helst 31 minuter till 365 dagar (dvs. 1 år) sedan den senaste gången s.getNewRepeat() anropades, kommer följande kod att anges som s.eVar1 lika med värdet för &quot;Repeat&quot; och fortsätter att ange s.eVar1 lika med värdet för &quot;Repeat&quot; (med varje nytt anrop) under resten av besökaren Vi besöker sajten.

```js
s.eVar1=s.getNewRepeat(365);
```

### Exempel 5

Om besökaren inte har varit på webbplatsen på minst 365 dagar (dvs. 1 år) sedan den senaste gången s.getNewRepeat() anropades, kommer följande kod att anges som s.eVar1 lika med värdet för &quot;New&quot; och kommer att fortsätta att anges som s.eVar1 lika med värdet för &quot;New&quot; (med varje nytt anrop) under resten av besökarens besök till sajten.

```js
s.eVar1=s.getNewRepeat(365);
```

## Versionshistorik

### 2.1 (30 september 2019)

* Ordna om JavaScript-logiken för att minska plugin-programmets storlek

### 2.0 (16 april 2018)

* Kompilerad med mindre kodstorlek
* Det gick inte att namnge cookien för att lagra besöksinformationen. Plugin-programmet namnger nu cookien dynamiskt baserat på det värde som skickas till `d` argumentet.
