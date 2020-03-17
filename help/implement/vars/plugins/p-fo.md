---
title: p_fo (endast sida först)
description: Se till att vissa rutiner bara aktiveras en gång per sida.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: p_fo (endast sida först)

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin- `p_fo` programmet är ett verktyg som kontrollerar om det finns ett specifikt JavaScript-objekt. Om objektet inte finns skapar plugin-programmet objektet och returnerar `true`. Om JavaScript-objektet redan finns på sidan returneras det `false`. Denna plugin är användbar för att köra kod exakt en gång på en sida. Flera andra plugin-program använder den här koden för att fungera. Denna plugin behövs inte om du inte är orolig för hur många gånger koden körs på en sida eller om du inte använder några beroende plugin-program.

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
   * Åtgärdstyp: Initiera p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `p_fo`

* **on** (required, string): Namnet på det JavaScript-objekt som skapas av plugin-programmet om objektet inte finns på sidan än.

Om objektet ännu inte finns returneras `true` och skapas objektet. Om objektet redan finns returnerar metoden `false`.

## Exempelanrop

### Exempel 1

Följande kod kontrollerar om det finns ett &quot;myobject&quot;-objekt på sidan.  Om &quot;myobject&quot;-objektet inte finns, skapar koden &quot;myobject&quot;-objektet och returnerar värdet true.  Därför kommer koden i villkorssatsen (t.ex. Console.log(&#39;hello&#39;);) att köras.

Å andra sidan, om objektet &quot;myobject&quot; redan finns när anropet p_fo inträffar, returnerar funktionen p_fo värdet false och villkorssatsen betraktas därför som false.  I det här fallet kommer koden i villkorssatsen inte att köras.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**OBS!** Varje gång ett nytt sidobjekt/DOM läses in (eller den aktuella sidan läses in igen), kommer det objekt som anges i on-argumentet inte längre att finnas och plug-in p_fo returnerar alltså true igen första gången den körs efter att sidan har lästs in.

## Versionshistorik

### 2.0

* Punktrelease (omkompilerad, mindre kodstorlek).
* Ändrad typ av returvärde från heltal till booleskt värde

### 1.0

* Ursprunglig version.
