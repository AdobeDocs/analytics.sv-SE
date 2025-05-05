---
title: s_gi()
description: Skapa och spåra instanser av AppMeasurement.
feature: Variables
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# s_gi

Funktionen `s_gi()` instansierar eller söker efter en instans av AppMeasurementet med hjälp av ett rapportsvit-ID. AppMeasurementet håller reda på alla instanser som skapas och `s_gi()` returnerar den befintliga instansen för en rapportserie om det finns någon. Om en instans inte finns skapas en ny instans.

## Instansiera ett spårningsobjekt med hjälp av Web SDK-tillägget

Tillägget Web SDK instansierar och hanterar spårningsobjektet åt dig. Du kan dock anpassa spårningsobjektets namn i tilläggsinställningarna:

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Experience Platform Web SDK.
1. Ändra fältet [!UICONTROL Name] till önskat värde. Dess standardvärde är `alloy`.

## Instansiera ett spårningsobjekt manuellt när Web SDK implementeras

Följande kod läser in Web SDK och instansierar ett spårningsobjekt. Du kan anpassa spårningsobjektets namn genom att ändra strängen `"alloy"` i slutet av det infogade skriptet till det önskade värdet.

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

Mer information finns i [Installera SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=sv-SE) i Web SDK-dokumentationen.

## Instansiera ett spårningsobjekt med Adobe Analytics-tillägget

Tillägget Analytics instansierar och hanterar spårningsobjektet åt dig. Du kan dock även ange ett globalt spårningsobjekt i dragspelet [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL Library Management] och markera en annan alternativknapp än [!UICONTROL Manage the library for me].

I det globala textfältet för variabeln kan du ange ett anpassat spårningsobjekt. Dess standardvärde är `s`.

## s_gi() i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Anropa funktionen `s_gi()` för att instansiera ett spårningsobjekt. Dess enda argument innehåller en kommaavgränsad sträng med ID:n för rapportsviten. Argumentet för rapportsvitens ID krävs.

>[!TIP]
>
>Adobe rekommenderar att du använder variabeln `s` som ett spårningsobjekt. Adobe använder `s` i sin dokumentation, sina implementeringsexempel och sina plugin-program. Du kan dock använda valfri variabel så länge du är konsekvent på webbplatsen.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Följande avsnitt och exempel innehåller komplexa implementeringsämnen. Testa implementeringen noggrant och spåra viktiga anpassningar i din organisations [lösningsdesigndokument](../../prepare/solution-design.md).

## Hantera flera implementeringar med olika spårningsobjekt

Du kan skicka olika data till olika rapportsviter om du instansierar flera spårningsobjekt. Dessa två spårningsobjekt fungerar oberoende av varandra.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Återställa variabler för AppMeasurementet när objektet har skrivits över

Vissa tredjepartsverktyg kan också använda JavaScript `s`-objektet. Om du av misstag skriver över objektet `s` på platsen kan du anropa `s_gi` med samma RSID-strängargument för att återställa alla överskrivna variabler och metoder.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Referera till samma spårningsobjekt med flera variabler

Om två variabler refererar till samma `s_gi()`-funktion med samma rapportserie kan du använda variablerna omväxlande.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
