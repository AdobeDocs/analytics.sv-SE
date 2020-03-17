---
title: avbryta
description: Variabeln abort är en boolesk variabel som förhindrar att en träff skickas till Adobes datainsamlingsservrar.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# avbryta

Variabeln `abort` är en boolesk variabel som kan förhindra att nästa spårningsanrop skickas till Adobe.

## Använda variabeln abort i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## AppMeasurement-syntax och anpassad kodredigerare i Launch

Variabeln `abort` är boolesk. Dess standardvärde är `false`.

* Om värdet anges `true`skickas inga data till Adobe vid nästa spårningsanrop (`t()` eller `tl()`).
* Om variabeln anges till `false` eller inte definieras händer ingenting.

```js
s.abort = true;
```

> [!NOTE] Variabeln återställs `abort` till `false` efter varje spårningsanrop. Om du behöver avbryta efterföljande spårningsanrop på samma sida anger du `abort` till `true` igen.

## Exempel

Variabeln `abort` kan anges i `doPlugins()` funktionen, som är den sista funktionen som körs innan en bildbegäran skickas till Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Du kan centralisera den logik som du använder för att identifiera aktiviteter som du inte vill spåra, till exempel vissa anpassade länkar eller externa länkar i visningsannonser.
