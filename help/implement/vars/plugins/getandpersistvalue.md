---
title: getAndPersistValue
description: Lagra ett värde som kan hämtas senare när som helst.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getAndPersistValue

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getAndPersistValue` plugin-programmet kan du lagra ett värde i en cookie som kan hämtas senare under ett besök. Den har en liknande roll som [!UICONTROL Storage duration] funktionen i Adobe Experience Platform Launch. Adobe rekommenderar att du använder denna plugin om du automatiskt vill behålla en Analytics-variabel på samma värde i efterföljande träffar efter att variabeln har angetts. Detta plugin-program är inte nödvändigt om Launch [!UICONTROL Storage duration] -funktionen är tillräcklig eller om du inte behöver ställa in och behålla variabler till samma värde i efterföljande träffar. Den inbyggda eVars-beständigheten kräver inte att denna plugin används eftersom dessa variabler finns kvar på serversidan av Adobe.

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
   * Åtgärdstyp: Initiera getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getAndPersist`

* **`vtp`** (obligatoriskt): Värdet som ska behållas från sida till sida
* **`cn`** (valfritt): Namnet på den cookie som värdet ska lagras i. Om det här argumentet inte anges får cookien ett namn `"s_gapv"`
* **`ex`** (valfritt): Antalet dagar innan cookien förfaller. Om argumentet är `0` eller inte är inställt upphör cookien att gälla när besöket är slut (30 minuters inaktivitet).

Om variabeln i `vtp` argumentet är inställd ställer plugin-programmet in cookien och returnerar sedan cookie-värdet. Om variabeln i `vtp` argumentet inte är inställd returnerar plugin-programmet bara cookie-värdet.

## Exempel

### Exempel 1

I följande kod ställs eVar21 in på samma värde som &quot;hello&quot;.  Koden ställer sedan in ev21gapv-cookien, som upphör att gälla om 28 dagar, som är lika med värdet för eVar21 (dvs. &quot;hej&quot;).  Koden ställer sedan (re) in eVar21 som lika med värdet för ev21gapv-cookien.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 2

Anta att eVar21 inte har angetts på den aktuella sidan än, men att inställningen var lika med &quot;hello&quot; på en tidigare sida under de senaste 28 dagarna.   Följande kod ställer bara in eVar21 som är lika med värdet för ev21gapv-cookien (d.v.s. &quot;hej&quot;).  Ev21gapv-cookien återställs inte eftersom eVar21 inte ställdes in på den aktuella sidan innan funktionen anropades.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 3

Anta att eVar21 inte har angetts på den aktuella sidan än, men att inställningen var lika med &quot;hello&quot; på en tidigare sida under de senaste 28 dagarna.  Följande kod ställer bara in prop35 som är lika med värdet för ev21gapv-cookien (d.v.s. &quot;hej&quot;).  Det kommer inte att ställa in eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 4

I följande kod anges eVar21 som lika med värdet för &quot;howdy&quot;.  Koden kommer sedan att ställa in (eller återställa) den v21gapv-cookien, som upphör att gälla om 28 dagar, som är lika med värdet för eVar21 (dvs. &quot;hur&quot;).  Koden ställer sedan in prop35 som är lika med värdet för ev21gapv-cookien (dvs. &quot;hur&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 5

Anta att s.eVar21 inte har angetts på några sidor under de senaste 28 dagarna.  Följande kod ställer in s.eVar21 till ingenting eftersom ev21gapv-cookien skulle ha gått ut 28 dagar efter att den senast ställdes in.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exempel 6

Följande kod ställer in eVar30 till &quot;shopping&quot;.  Sedan ställs s_gapv-cookien in, som upphör att gälla i slutet av webbläsarsessionen, som är lika med värdet för s.eVar30 (dvs. &quot;handla&quot;).  Sedan ställs s.eVar30 in som lika med värdet för s_gapv-cookien (dvs. anropet getAndPersistValue returnerar värdet för s_gapv-cookien, som i det här fallet är &quot;handla&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Om s.eVar30 inte är inställd på ett explicit värde på eventuella ytterligare sidor som visas under sessionen, utan är inställd (in doPlugins) via följande kod..

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 anges som lika med &quot;handla&quot; (dvs. det beständiga värdet för s_gapv-cookien)

## Versionshistorik

### 2.0 (16 april 2018)

* Point release (mindre kodstorlek)
* Om 0 skickas in i `ex` argumentet upphör det att gälla efter 30 minuters inaktivitet i stället för att upphöra i slutet av webbläsarsessionen.

### 1.0 (18 januari 2016)

* Ursprunglig version.
