---
title: getTimeBetweenEvents
description: Mät tiden mellan två händelser.
feature: Variables
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Adobe plug-in: getTimeBetweenEvents

{{plug-in}}

Med plugin-programmet `getTimeBetweenEvents` kan du hålla reda på hur lång tid det tar mellan två Analytics-händelser, inklusive kundvagn och anpassade händelser. Det är användbart för att spåra hur lång tid det tar för en utcheckningsprocess att slutföra eller för andra processer som du vill mäta tid. Denna plugin behövs inte om du inte har några konverteringsprocesser som du vill mäta hur lång tid de tar.

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
   * Åtgärdstyp: Initiera getTimeBetweenEvents
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken [!UICONTROL Configure tracking using custom code] som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurementet

Kopiera och klistra in följande AppMeasurement var som helst i analysfilen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getTimeBetweenEvents` använder följande argument:

* **`ste`** (obligatoriskt, sträng): Starta timerhändelser. En kommaavgränsad sträng med Analytics-händelser för att&quot;starta timern&quot;.
* **`rt`** (obligatoriskt, booleskt): Starta om timeralternativet. Ange `true` om du vill starta om timern varje gång variabeln `events` innehåller en starttidshändelse. Ange `false` om du inte vill att timern ska startas om när en starttimerhändelse visas.
* **`stp`** (obligatoriskt, sträng): Stoppa timerhändelser. En kommaavgränsad sträng med Analytics-händelser som&quot;stoppar timern&quot;.
* **`res`** (obligatoriskt, booleskt): Återställ timeralternativ. Ange `true` om du vill registrera tiden sedan timern startades OCH återställa timern efter att den stoppats. Ange `false` om du vill spela in tiden men inte stoppa timern. Om värdet är `false` fortsätter timern att köras efter det att händelsvariabeln har registrerat en stop-händelse.

  >[!TIP]
  >
  >Om du anger det här argumentet som `false` bör du ange argumentet `rte` nedan.
* **`cn`** (valfri sträng): Det cookie-namn där tidpunkten för den första händelsen lagras. Standardvärdet är `"s_tbe"`.
* **`etd`** (valfritt, heltal): Förfallotiden för cookien i dagar. Ange till `0` om du vill förfalla i slutet av webbläsarsessionen. Standardvärdet är 1 dag om den inte anges.
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
* **`bml`** (valfritt, tal): Längden på avrundningsriktmärket enligt formatet för argumentet `fmt`. Om argumentet `fmt` till exempel är `"s"` och det här argumentet är `2`, avrundas returvärdet till närmaste 2-sekunders test. Om argumentet `fmt` är `"m"` och det här argumentet är `0.5` avrundas returvärdet till närmaste halveringstips.
* **`rte`** (valfri sträng): Kommaavgränsad sträng med Analytics-händelser som tar bort eller tar bort timern. Standardvärdet är ingenting.

När den här funktionen anropas returneras ett heltal som representerar tiden mellan starthändelsen och stopphändelsen timer i det önskade formatet.

## Exempelanrop

```js
// The timer starts or restarts when the events variable contains event1
// The timer stops and resets when the events variable contains event2
// The timer resets when the events variable contains event3 or the visitor closes their browser
// Sets eVar1 to the number of seconds between event1 and event2, rounded to the nearest 2-second benchmark
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");

// The timer starts when the events variable contains event1. It does NOT restart with subsequent hits that also contain event1
// The timer records a "lap" when the events variable contains event2. It does not stop the timer.
// The timer resets when the events variable contains event3 or if more than 20 days pass since the timer started
// The timer is stored in a cookie labeled "s_20"
// Sets eVar4 to the number of hours between event1 and event2, rounded to the nearest 90-minute benchmark
s.eVar4 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");

// Similar to the above timer in eVar4, except the return value is returned in seconds/minutes/hours/days depending on the timer length.
// The timer expires after 1 day.
s.eVar4 = getTimeBetweenEvents("event1", true, "event2", true);
```

## Tidigare versioner

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.1 (26 maj 2018)

* Anpassar ändringar som gjorts i den nya versionen av plugin-programmet `formatTime`.

### 2.0 (6 april 2018)

* Fullständig omskrivning/omanalys av plugin-program.
