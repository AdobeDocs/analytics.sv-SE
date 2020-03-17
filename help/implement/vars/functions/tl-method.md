---
title: tl
description: Skicka ett länkspårningssamtal till Adobe.
translation-type: tm+mt
source-git-commit: 8494e8bb08b45006b357dd114e6bf9507f0cd54a

---


# tl

Metoden är en viktig `tl` komponent i Adobe Analytics. Den tar alla analysvariabler som definieras på sidan, kompilerar dem till en bildbegäran och skickar dessa data till Adobes datainsamlingsservrar. Den fungerar på ungefär samma sätt som `t` metoden, men den här metoden ökar inte sidvisningen. Den är användbar för att spåra länkar och andra element som inte skulle betraktas som en fullständig sidinläsning.

Om `trackDownloadLinks` eller `trackExternalLinks` är aktiverat anropar AppMeasurement automatiskt `tl` metoden för att skicka hämtningslänkar och avsluta länkspårningsdata. Om din organisation föredrar att ha större kontroll över länkarna och deras beteende kan du anropa `tl` metoden manuellt. Anpassade länkar kan bara spåras manuellt.

## Länkspårningssamtal i Adobe Experience Platform Launch

Launch har en dedikerad plats som anger ett länkspårningsanrop.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
1. Klicka på ikonen + [!UICONTROL Actions]under
1. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] &quot; [!UICONTROL Action Type] Skicka Beacon&quot;.
1. Klicka på `s.tl()` alternativknappen.

Du kan inte ange några valfria argument i Launch.

## s.tl()-metoden i AppMeasurement och den anpassade kodredigeraren Launch

Anropa `s.tl()` metoden när du vill skicka ett spårningsanrop till Adobe.

```js
s.tl();
```

Den här metoden kan också innehålla flera argument:

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Länkobjekt

Argumentet för läntobjekt avgör om webbläsaren väntar upp till 500 ms innan den navigerar bort från sidan. Om en bildbegäran skickas tidigare än 500 ms navigerar sidan direkt till den klickade länken.

> [!NOTE] Med AppMeasurement aktiveras automatiskt variabeln `useBeacon` för avslutningslänkar, vilket gör att det här argumentet inte längre behövs i moderna webbläsare. Det här argumentet användes oftare i tidigare versioner av AppMeasurement.

* `this`: Vänta i upp till 500 ms för att ge AppMeasurement tid att skicka en bildbegäran. Standardvärde.
* `true`: Vänta inte.

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Länktyp

Argumentet för länktyp är en sträng med en bokstav som avgör typen av länkspårningsanrop. Det är samma sak som att ställa in `linkType` variabeln.

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Länknamn

Argumentet för länknamn är en sträng som avgör dimensionsvärdet för länkspårning. Det är samma sak som att ställa in `linkName` variabeln.

```js
s.tl(true,"d","Example download link");
```

### Variabla åsidosättningar

Gör att du kan ändra variabelvärden för ett enskilt anrop. Mer information finns i [Variabelåsidosättningar](../../js/overrides.md) .

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

Använd JavaScript för att göra samma grundläggande anrop för länkspårning med hjälp av olika variabler:

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
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

Om `trackDownloadLinks` eller `trackExternalLinks` är aktiverade gör AppMeasurement automatiskt ett länkspårningsanrop om rätt filter matchar. Om du även ringer `s.tl()` manuellt för dessa länkklick kan du skicka duplicerade data till Adobe. Duplicerade data ökar rapportnummer och gör dem mindre exakta.

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
