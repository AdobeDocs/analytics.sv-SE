---
title: getTimeBetweenEvents
description: Mät tiden mellan två händelser.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getTimeBetweenEvents

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getTimeBetweenEvents` plugin-programmet kan du hålla reda på hur lång tid det tar mellan två olika Analytics-händelser, inklusive kundvagn och anpassade händelser. Det är användbart för att spåra hur lång tid det tar för en utcheckningsprocess att slutföra eller för andra processer som du vill mäta tid. Denna plugin behövs inte om du inte har några konverteringsprocesser som du vill mäta hur lång tid de tar.

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
   * Åtgärdstyp: Initiera getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getTimeBetweenEvents`

* **`ste`** (required, string): Starta timerhändelser. En kommaavgränsad sträng med Analytics-händelser för att&quot;starta timern&quot;.
* **`rt`** (obligatoriskt, booleskt): Starta om tidsinställningen. Ange till `true` om du vill starta om timern varje gång variabeln `events` innehåller en starttidshändelse. Ange till `false` om du inte vill att timern ska starta om när en starttidsinställningshändelse visas.
* **`stp`** (required, string): Stoppa timerhändelser. En kommaavgränsad sträng med Analytics-händelser som&quot;stoppar timern&quot;.
* **`res`** (obligatoriskt, booleskt): Återställ alternativet Timer. Ange till `true` om du vill registrera tiden sedan timern startades OCH återställa timern efter att den stoppats. Ange till `false` om du vill spela in tiden men inte stoppa timern. Om det anges till `false`fortsätter timern att köras efter det att händelsemabeln har registrerat en stop-händelse.
   > [!TIP] Om du ställer in det här argumentet på `false`bör du ställa in `rte` argumentet nedan.
* **`cn`** (valfri, sträng): Det cookie-namn där tidpunkten för den första händelsen lagras. Standardvärdet är `"s_tbe"`.
* **`etd`** (valfritt, heltal): Förfallotid för cookien i dagar. Anges `0` till förfallodatum i slutet av webbläsarsessionen. Standardvärdet är 1 dag om den inte anges.
* **`fmt`** (valfri, sträng): Formatet på den tid som antalet sekunder returneras i (standardvärdet är ingenting)
   * `"s"` i sekunder
   * `"m"` i minuter
   * `"h"` i timmar
   * `"d"` i dagar
   * Om det inte anges baseras returvärdets format på följande regler:
      * Allt som är mindre än en minut avrundas till närmaste 5-sekunders test. Exempel: 10 sekunder, 15 sekunder
      * Allt som är mellan en minut och en timme avrundas till närmaste 1/2-minuters test. Exempel: 30,5 minuter, 31 minuter
      * Allt som är mellan en timme och en dag avrundas till närmaste kvartalstimmar. Exempel: 2,25 timmar, 3,5 timmar
      * Allt som är större än en dag avrundas till närmaste dag. Exempel: 1 dag, 3 dagar, 9 dagar
* **`bml`** (valfritt, tal): Längden på avrundningsriktmärket enligt `fmt` argumentets format. Om argumentet till exempel är `fmt` och det här argumentet är `"s"` `2`avrundas returvärdet till närmaste tvåsekundersriktmärke. Om `fmt` argumentet är `"m"` och detta argument är `0.5`avrundas returvärdet till närmaste halveringstips.
* **`rte`** (valfri, sträng): Kommaavgränsad sträng med Analytics-händelser som tar bort eller tar bort timern. Standardvärdet är ingenting.

Om du anropar den här metoden returneras ett heltal som representerar tiden mellan starthändelsen och stopphändelsen timer i det önskade formatet.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...är konfigurerad att bete sig på följande sätt:

* Timern startar när s.events innehåller event1.
* Timern startas om varje gång s.events innehåller event1
* Timern stoppas när s.events innehåller event2
* Timern återställs (dvs. gå till 0 sekunder) varje gång s.events innehåller event2
* Timern återställs också när s.events innehåller event3 ELLER om besökaren stänger sin webbläsare
* När en faktisk tid mellan event1 och event2 spelas in, ställer plugin-programmet in eVar1 som lika med antalet sekunder mellan de två händelser som ställs in, avrundat till närmaste 2-sekunders test (t.ex. 0 sekunder, 2 sekunder, 4 sekunder, 10 sekunder, 184 sekunder osv.)
* Om s.events innehåller event2 innan en timer har startats, kommer eVar1 inte att anges alls.

### Exempel 2

Följande kod...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...är konfigurerad att bete sig på följande sätt:

* Timern startar när s.events innehåller event1.
* Timern startar INTE om varje gång som s.events innehåller event1, utan den ursprungliga timern fortsätter ändå att köras
* Timern stoppas INTE när s.events innehåller event2, men plugin-programmet spelar in tiden sedan den ursprungliga inställningen för event1 spelades in
* Timern lagras i en cookie med namnet&quot;s_20&quot;
* Timern återställs endast när s.events innehåller event3 ELLER om 20 dagar har gått sedan timern startades
* När en tid mellan (den ursprungliga) händelse1 och händelse2 registreras, kommer plugin-programmet att ställa in eVar1 lika med antalet timmar mellan de två händelser som ställs in, avrundat till närmaste 1/2-timmars riktmärke (t.ex. 0 timmar, 1,5 timmar, 3 timmar, 7,5 timmar, 478,5 timmar osv.)

### Exempel 3

Följande kod...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...kommer att ge liknande resultat som i det första exemplet ovan, värdet för eVar1 returneras i sekunder, minuter, timmar eller dagar, beroende på timerns slutliga längd.  Timern förfaller 1 dag efter att den först ställdes in i stället för när besökaren stänger sin webbläsare.

## Versionshistorik

### 2.1 (26 maj 2018)

* Anpassar ändringar som gjorts i den nya versionen av `formatTime` plugin-programmet.

### 2.0 (6 april 2018)

* Fullständig omskrivning/omanalys av plugin-program.
