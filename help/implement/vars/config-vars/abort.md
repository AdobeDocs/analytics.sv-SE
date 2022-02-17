---
title: avbryt
description: Variabeln abort är en boolesk variabel som förhindrar att en träff skickas till datainsamlingsservrar i Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# avbryt

The `abort` är en boolesk variabel som kan förhindra att nästa spårningsanrop skickas till Adobe.

## Använda variabeln abort i användargränssnittet för datainsamling i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## AppMeasurement-syntax och anpassad kodredigerare i användargränssnittet för datainsamling

The `abort` är en boolesk variabel. Standardvärdet är `false`.

* Om inställt på `true`, nästa spårningsanrop ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)) skickar inga data till Adobe.
* Om inställt på `false` eller inte är definierad gör den här variabeln ingenting.

```js
s.abort = true;
```

>[!NOTE]
>
>The `abort` variabeln återställs till `false` efter varje spårningssamtal. Om du behöver avbryta efterföljande spårningsanrop på samma sida anger du `abort` till `true` igen.

## Exempel

The `abort` kan anges i [`doPlugins()`](../functions/doplugins.md) -funktion, som är den sista funktionen som körs innan en bildbegäran skickas till Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Du kan centralisera den logik som du använder för att identifiera aktiviteter som du inte vill spåra, till exempel vissa anpassade länkar eller externa länkar i visningsannonser.
