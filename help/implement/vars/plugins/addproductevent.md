---
title: addProductEvent
description: Lägger till anpassade händelser i variabeln products and events.
translation-type: tm+mt
source-git-commit: 7a455fb9eb355617bab016218b171dffa8d21958

---


# Adobe plug-in: addProductEvent

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin- `addProductEvent` programmet lägger till en numerisk händelse eller valutakurs i `products` variabeln. Adobe rekommenderar att du använder det här plugin-programmet om du vill lägga till en numerisk händelse eller valutakändelse i `products` variabeln utan att behöva oroa dig för produktsträngformatet. Detta plugin-program är inte nödvändigt om du inte använder numeriska händelser eller valutakändelser i `products` variabeln.

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
   * Åtgärdstyp: Initiera addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `addProductEvent`

* **`en`** (required, string): Händelsen som ska läggas till i den sista posten i `products` variabeln. Om `products` variabeln är tom skapas en&quot;tom&quot; produktpost med händelsen (och dess värde) bifogad.
* **`ev`** (required, string): Värdet som tilldelas till den numeriska händelsen eller valutakurshändelsen i `en` argumentet.  Standardvärdet är `1` när det inte anges.
* **`ap`** (valfritt, boolesk): Om variabeln products för närvarande innehåller mer än en produktpost läggs händelsen till i alla produktposter med värdet `true` (eller `1`).  Standardvärdet är `false` när det inte anges.

Ingenting `addProductEvent` returneras. I stället läggs händelsen och dess värde till i `products` variabeln. Plugin-programmet lägger automatiskt till händelsen i `events` variabeln, eftersom den också krävs där.

## Cookies

Plugin-programmet addProductEvent skapar eller använder inga cookies

## Exempelanrop

### Exempel 1

I följande kod anges variabeln `s.products` till `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

Ovanstående kod ställer också in `s.events` variabeln på `"purchase,event35"`

### Exempel 2

Följande kod ställer in variabeln på `s.products``";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

När det tredje argumentet i `addProductEvent` anropet är `true` (eller `1`), har varje produktpost den händelse som anges i anropet lagts till i värdet.

### Exempel 3

Följande kod ställer in variabeln på `s.products``";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

Ovanstående kod ställer också in `s.events` variabeln på `"purchase,event2,event33,event34,event35"`

### Exempel 4

Följande kod ställer in variabeln på `s.products``";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

Ovanstående kod ställer också in variabeln `s.events` till `"purchase,event2,event33,event34,event35"`.

> [!NOTE] Det andra argumentet i anropet kan vara antingen ett heltal **eller** en sträng som representerar ett heltal/tal

### Exempel 5

Om `s.products` inte redan är inställt anges det i följande kod `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

Ovanstående kod läggs också `"event35"` till i slutet av `s.events` eller **, om den** inte redan är inställd, anges ovanstående kod `s.events` `s.events` till `"event35"`

## Versionshistorik

### 1.0 (7 oktober 2019)

* Ursprunglig version.
