---
title: getTimeBetweenEvents
description: Mät tiden mellan två händelser.
translation-type: tm+mt
source-git-commit: e8c6f4bbc72f7edfd966d698b8e4678e5eaa739e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 0%

---


# Adobe plug-in: getTimeBetweenEvents

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `getTimeBetweenEvents` kan du hålla reda på hur lång tid som helst mellan två Analytics-händelser, inklusive kundvagn och anpassade händelser. Det är användbart för att spåra hur lång tid det tar för en utcheckningsprocess att slutföra eller för andra processer som du vill mäta tid. Denna plugin behövs inte om du inte har några konverteringsprocesser som du vill mäta hur lång tid de tar.

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
   * Åtgärdstyp: Initiera getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `getTimeBetweenEvents` använder följande argument:

* **`ste`** (required, string): Starta timerhändelser. En kommaavgränsad sträng med Analytics-händelser för att&quot;starta timern&quot;.
* **`rt`** (obligatoriskt, booleskt): Starta om tidsinställningen. Ange `true` om du vill starta om timern varje gång variabeln `events` innehåller en starttimerhändelse. Ange `false` om du inte vill att timern ska starta om när en starttimerhändelse visas.
* **`stp`** (required, string): Stoppa timerhändelser. En kommaavgränsad sträng med Analytics-händelser som&quot;stoppar timern&quot;.
* **`res`** (obligatoriskt, booleskt): Återställ alternativet Timer. Ange `true` om du vill registrera tiden sedan timern startades OCH återställa timern efter att den stoppats. Ange `false` om du vill spela in tiden men inte stoppa timern. Om den anges till `false` fortsätter timern att köras efter det att händelsvariabeln har registrerat en stop-händelse.

   >[!TIP]
   >
   >Om du anger det här argumentet som `false` bör du ange argumentet `rte` nedan.
* **`cn`** (valfri, sträng): Det cookie-namn där tidpunkten för den första händelsen lagras. Standardvärdet är `"s_tbe"`.
* **`etd`** (valfritt, heltal): Förfallotid för cookien i dagar. Ange `0` som förfaller i slutet av webbläsarsessionen. Standardvärdet är 1 dag om den inte anges.
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
* **`bml`** (valfritt, antal): Längden på avrundningsriktmärket enligt  `fmt` argumentets format. Om argumentet `fmt` till exempel är `"s"` och det här argumentet är `2`, avrundas returvärdet till närmaste 2-sekundersreferens. Om `fmt`-argumentet är `"m"` och det här argumentet är `0.5`, avrundas returvärdet till närmaste halveringstips.
* **`rte`** (valfri, sträng): Kommaavgränsad sträng med Analytics-händelser som tar bort eller tar bort timern. Standardvärdet är ingenting.

Om du anropar den här metoden returneras ett heltal som representerar tiden mellan starthändelsen och stopphändelsen timer i det önskade formatet.

## Exempelanrop

### Exempel 1

Följande kod...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...är konfigurerad att bete sig på följande sätt:

* Timern startar när s.events innehåller event1.
* Timern startas om varje gång s.events innehåller event1
* Timern stoppas när s.events innehåller event2
* Timern återställs (dvs. gå till 0 sekunder) varje gång s.events innehåller event2
* Timern återställs också när s.events innehåller event3 ELLER om besökaren stänger sin webbläsare
* När en faktisk tid mellan event1 och event2 spelas in, ställer plugin-programmet in eVar1 som lika med antalet sekunder mellan de två händelser som ställs in, avrundat till närmaste 2-sekunders test (t.ex. 0 sekunder, 2 sekunder, 4 sekunder, 10 sekunder, 184 sekunder osv.)
* Om s.events innehåller event2 innan en timer har startats, ställs inte eVar1 in alls.

### Exempel 2

Följande kod...

```js
s.eVar1 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...är konfigurerad att bete sig på följande sätt:

* Timern startar när s.events innehåller event1.
* Timern startar INTE om varje gång som s.events innehåller event1, utan den ursprungliga timern fortsätter ändå att köras
* Timern stoppas INTE när s.events innehåller event2, men plugin-programmet spelar in tiden sedan den ursprungliga inställningen för event1 spelades in
* Timern lagras i en cookie med namnet&quot;s_20&quot;
* Timern återställs endast när s.events innehåller event3 ELLER om 20 dagar har gått sedan timern startades
* När en tid mellan (ursprunglig) händelse1 och händelse2 registreras, kommer plugin-programmet att ställa in eVar1 som lika med antalet timmar mellan de två händelser som ställs in, avrundat till närmaste 1/2-timmars riktmärke (t.ex. 0 timmar, 1,5 timmar, 3 timmar, 7,5 timmar, 478,5 timmar osv.)

### Exempel 2

Följande kod...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true);
```

...kommer att ge liknande resultat som i det första exemplet ovan, värdet för eVar1 returneras i sekunder, minuter, timmar eller dagar, beroende på timerns slutliga längd.  Timern förfaller 1 dag efter att den först ställdes in i stället för när besökaren stänger sin webbläsare.

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (26 maj 2018)

* Anpassar ändringar som gjorts i den nya versionen av plugin-programmet `formatTime`.

### 2.0 (6 april 2018)

* Fullständig omskrivning/omanalys av plugin-program.
