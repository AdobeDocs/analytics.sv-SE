---
title: addProductEvar
description: Lägger till eVars för försäljning i variabeln products.
translation-type: tm+mt
source-git-commit: abed7197898d6c27448069350c9f2217d58293c4
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 1%

---


# Adobe plug-in: addProductEvar

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `addProductEvar` kan du enkelt lägga till en Adobe Analytics-eVar som använder produktsyntax i variabeln products utan att behöva bekymra dig om det redan befintliga innehållet i variabeln products ska ändras/flyttas/tas bort. Adobe rekommenderar att du använder denna plugin om du enkelt vill lägga till produktsyntaxer för varuexponering av eVars i variabeln [`products`](../page-vars/products.md). Du behöver inte använda plugin-programmet `addProductEvar` om du inte använder eVars för försäljning med produktsyntax.

>[!NOTE]
>
>Denna plugin ersätter inte eVars som redan finns i en produktpost. Det lägger bara till värden som du anger med det här plugin-programmet. Var försiktig när du lägger till eVars som redan finns för den produkten.

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
   * Åtgärdstyp: Initiera addProductEvar
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
/* Adobe Consulting Plugin: addProductEvar v2.0 */
function addProductEvar(en,ev,ap){var e=en,f=ev,d=ap;if("-v"===e)return{plugin:"addProductEvar",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}if("undefined"!==typeof b&&(b.contextData.addProductEvar="2.0","string"===typeof e&&"string"===typeof f&&""!==f))if(d=d||!1,b.products){c=b.products.split(",");var g=c.length;d=d?0:g-1;for(var a;d<g;d++)a=c[d].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+e+"="+f:a[5]?a[5]=e+"="+f:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=e+"="+f),c[d]=a.join(";");b.products=c.join(",")}else b.products=";;;;;"+e+"="+f};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Plugin-programmet `addProductEvar` använder följande argument:

* **`en`** (required, string): eVar som ska läggas till i den sista posten som finns i variabeln products. Om variabeln products är tom skapar plugin-programmet en tom produktpost med det eVar som är bifogat till slutet av posten.
* **`ev`** (required, string): Värdet som tilldelats eVar.
* **`ap`** (valfritt, boolesk): Om variabeln products för närvarande innehåller mer än en produktpost läggs värdet true (eller 1) till i  **** alla produktposter.  Standardvärdet är false (eller 0), vilket innebär att eVar läggs till endast i den **sista**-posten som finns i produktvariabeln.

Plugin-programmet `addProductEvar` returnerar ingenting. I stället läggs eVar (och eVar) som anges i argumentet `en` och `ev` till i variabeln `products`.

## Exempel

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium");
s.addProductEvar("eVar24", "women");
s.addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium", true);
s.addProductEvar("eVar24", "women", true);
s.addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
s.addProductEvar("eVar1", "blue");
```

## Versionshistorik

### 2.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.0 (7 oktober 2019)

* Ursprunglig version.
