---
title: tl
description: Skicka ett länkspårningsanrop till Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# tl

The `tl()` är en viktig komponent i Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar data till datainsamlingsservrarna i Adobe. Det fungerar på liknande sätt som [`t()`](t-method.md) den här metoden ökar dock inte sidvisningen. Den är användbar för att spåra länkar och andra element som inte skulle betraktas som en fullständig sidinläsning.

If [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) eller [`trackExternalLinks`](../config-vars/trackexternallinks.md) är aktiverade, AppMeasurement anropar automatiskt `tl()` metod för att skicka hämtningslänk och avsluta länkspårningsdata. Om din organisation föredrar att ha större kontroll över länkarna och deras beteende kan du anropa `tl()` -metoden manuellt. Anpassade länkar kan bara spåras manuellt.

## Länkspårningsanrop med taggar i Adobe Experience Platform

Användargränssnittet för datainsamling har en dedikerad plats som anger ett länkspårningsanrop.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
1. Under [!UICONTROL Actions]klickar du på plustecknet (+)
1. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] för att skicka Beacon.
1. Klicka på `s.tl()` alternativknapp.

Du kan inte ange några valfria argument i användargränssnittet för datainsamling.

## s.tl(), metod i AppMeasurement och anpassad kodredigerare

Ring `s.tl()` när du vill skicka ett spårningsanrop till Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Länkobjekt (obligatoriskt)

Argumentet för läntobjekt avgör om webbläsaren väntar upp till 500 ms innan den navigerar bort från sidan. Om en bildbegäran skickas tidigare än 500 ms navigerar sidan direkt till den klickade länken.

>[!NOTE]
>
>AppMeasurement aktiverar automatiskt [`useBeacon`](../config-vars/usebeacon.md) variabel för att avsluta länkar, vilket gör att det här argumentet inte längre behövs i moderna webbläsare. Det här argumentet användes oftare i tidigare versioner av AppMeasurement.

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

* `o`: Länken är en [Egen länk](/help/components/dimensions/custom-link.md).
* `d`: Länken är en [Hämta länk](/help/components/dimensions/download-link.md).
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

Argumentet för länknamn är en sträng som avgör dimensionsobjektet för länkspårning. När du använder [Egen länk](/help/components/dimensions/custom-link.md), [Hämta länk](/help/components/dimensions/download-link.md), eller [Avsluta länk](/help/components/dimensions/exit-link.md) dimensioner i rapportering, den här strängen innehåller dimensionsobjektet. Om det här argumentet inte anges visas [linkURL](../config-vars/linkurl.md) -variabeln används.

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Variabla åsidosättningar (valfritt)

Gör att du kan ändra variabelvärden för ett enskilt anrop. Se [variabelåsidosättningar](../../js/overrides.md) för mer information.

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Exempel och användningsexempel

Skicka ett grundläggande länkspårningsanrop direkt i en HTML-länk:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Använd JavaScript för att göra ett grundläggande anrop för länkspårning med metodargument:

```JavaScript
s.tl(true,"o","Example link");
```

### Göra länkspårningsanrop i en anpassad funktion

Du kan konsolidera länkspårningskod i en fristående JavaScript-funktion som definieras på sidan eller i en länkad JavaScript-fil. Anrop kan sedan göras i funktionen onClick för varje länk. Ange följande i en JavaScript-fil:

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

### Undvik att spåra dubblettlänkar

If `trackDownloadLinks` eller `trackExternalLinks` är aktiverade gör AppMeasurement automatiskt ett länkspårningsanrop om rätt filter matchar. Om du även ringer manuellt `s.tl()` för dessa länkklick kan du skicka duplicerade data till Adobe. Duplicerade data ökar rapportnummer och gör dem mindre exakta.

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
