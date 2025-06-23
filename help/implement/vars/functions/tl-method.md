---
title: tl
description: Skicka ett länkspårningsanrop till Adobe.
feature: Appmeasurement Implementation
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 0%

---

# tl

Metoden `tl()` är en viktig kärnkomponent för Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar dessa data till Adobe datainsamlingsservrar. Den fungerar på ungefär samma sätt som metoden [`t()`](t-method.md), men den här metoden ökar inte sidvisningen. Den är användbar för att spåra länkar och andra element som inte skulle betraktas som en fullständig sidinläsning.

Om [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) eller [`trackExternalLinks`](../config-vars/trackexternallinks.md) är aktiverade anropar AppMeasurement automatiskt metoden `tl()` för att skicka hämtningslänkar och avsluta länkspårningsdata. Om din organisation föredrar att ha större kontroll över länkarna och deras beteende kan du anropa metoden `tl()` manuellt. Anpassade länkar kan bara spåras manuellt.

## Länkspårning med SDK för webben

SDK för webben skiljer inte mellan sidvisningsanrop och länkspårningsanrop. Båda använder kommandot `sendEvent`.

Om du använder ett XDM-objekt och vill att Adobe Analytics ska räkna en viss händelse som ett länkspårningsanrop, ska du kontrollera att dina XDM-data innehåller:

* Länknamn: mappat till `xdm.web.webInteraction.name`.
* Länk-URL: mappad till `xdm.web.webInteraction.URL`.
* Länktyp: mappad till `xdm.web.webInteraction.type`. Giltiga värden är `other` (anpassade länkar), `download` (hämtningslänkar) och `exit` (avsluta länkar).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

Om du använder ett dataobjekt och vill att Adobe Analytics ska räkna en viss händelse som ett länkspårningsanrop, ska du se till att dataobjektet innehåller:

* Länknamn: mappat till `data.__adobe.analytics.linkName`.
* Länk-URL: mappad till `data.__adobe.analytics.linkURL`.
* Länktyp: mappad till `data.__adobe.analytics.linkType`. Giltiga värden är `o` (anpassade länkar), `d` (hämtningslänkar) och `e` (avsluta länkar).

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## Länkspårning med Adobe Analytics-tillägget

Adobe Analytics-tillägget har en dedikerad plats där ett länkspårningsanrop kan ställas in.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
1. Klicka på önskad åtgärd under [!UICONTROL Actions] eller klicka på ikonen **+** för att lägga till en åtgärd.
1. Ställ in listrutan [!UICONTROL Extension] på **[!UICONTROL Adobe Analytics]** och [!UICONTROL Action Type] på **[!UICONTROL Send Beacon]**.
1. Klicka på alternativknappen `s.tl()`.

Du kan inte ange några valfria argument i Analytics-tillägget.

## s.tl()-metoden i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Anropa metoden `s.tl()` när du vill skicka ett spårningsanrop till Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Länkobjekt (obligatoriskt)

Argumentet för läntobjekt avgör om webbläsaren väntar upp till 500 ms innan den navigerar bort från sidan. Om en bildbegäran skickas tidigare än 500 ms navigerar sidan direkt till den klickade länken.

>[!NOTE]
>
>AppMeasurement aktiverar automatiskt variabeln [`useBeacon`](../config-vars/usebeacon.md) för avslutningslänkar, vilket gör att det här argumentet inte längre behövs i moderna webbläsare. Detta argument användes oftare i tidigare versioner av AppMeasurement.

* `this`: Vänta i upp till 500 ms för att ge AppMeasurement tid att skicka en bildbegäran. Standardvärde.
* `true`: Vänta inte.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Länktyp (obligatoriskt)

Argumentet för länktyp är en sträng med ett tecken som avgör typen av anrop för länkspårning. Det finns tre giltiga värden.

* `o`: Länken är en [anpassad länk](/help/components/dimensions/custom-link.md).
* `d`: Länken är en [hämtningslänk](/help/components/dimensions/download-link.md).
* `e`: Länken är en [Avsluta länk](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Länknamn (rekommenderas)

Argumentet för länknamn är en sträng som avgör dimensionsobjektet för länkspårning. När du använder dimensionerna [Egen länk](/help/components/dimensions/custom-link.md), [Hämta länk](/help/components/dimensions/download-link.md) eller [Avsluta länk](/help/components/dimensions/exit-link.md) i rapporter innehåller den här strängen dimensionsobjektet. Om det här argumentet inte anges används variabeln [linkURL](../config-vars/linkurl.md).

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Variabla åsidosättningar (valfritt)

Gör att du kan ändra variabelvärden för ett enskilt anrop. Mer information finns i [Variabelåsidosättningar](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Exempel och användningsexempel

Skicka ett enkelt länkspårningsanrop direkt i en HTML-länk:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Använd JavaScript för att göra ett grundläggande anrop för länkspårning med hjälp av metodargument:

```JavaScript
s.tl(true,"o","Example link");
```

### Göra länkspårningsanrop i en anpassad funktion

Du kan sammanställa länkspårningskod i en fristående JavaScript-funktion. Anrop kan sedan göras i funktionen `onClick` för varje länk. Ange följande i en JavaScript-fil:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

Du kan sedan anropa funktionen när du vill spåra en viss länk:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

>[!NOTE]
>Om du anropar metoden `tl()` indirekt kan det göra det enklare att rapportera övertäckningar i Activity Map. Du måste klicka på varje länk för att registrera funktionen med länkelementet. Activity Map dimensioner i Workspace spåras dock på samma sätt.

### Undvik att spåra dubblettlänkar

Om `trackDownloadLinks` eller `trackExternalLinks` är aktiverade gör AppMeasurement automatiskt ett länkspårningsanrop om rätt filter matchar. Om du även anropar `s.tl()` manuellt för de här länkklickningarna kan du skicka duplicerade data till Adobe. Duplicerade data ökar rapportnummer och gör dem mindre exakta.

Följande funktion skickar till exempel två länkspårningsanrop för samma länkklickning (manuella och automatiska hämtningslänkar):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Du kan förhindra dubblerade länkspårningsanrop genom att använda följande ändrade funktion. Först kontrolleras om ett läntobjekt finns och ett manuellt länkspårningsanrop skickas bara om läntobjektet är en tom sträng.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```

### Använd metoden `tl()` med Activity Map

Du kan använda metoden `tl()` för att spåra anpassade element och för att konfigurera övertäckningsåtergivning för dynamiskt innehåll. Parametern `linkName` används också för att ställa in dimensionen [Activity Map Link](/help/components/dimensions/activity-map-link.md) .

När metoden `tl()` anropas direkt från HTML-elementets on-click-händelse kan Activity Map visa en övertäckning för det elementet när webbsidan läses in. Exempel:

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

När metoden `tl()` inte anropas direkt från HTML-elementets on-click-händelse, kan Activity Map bara visa en övertäckning när användaren har klickat på det elementet. Exempel:

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```
