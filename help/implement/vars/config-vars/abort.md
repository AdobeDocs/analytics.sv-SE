---
title: avbryt
description: Variabeln abort är en boolesk variabel som förhindrar att en träff skickas till datainsamlingsservrar i Adobe.
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# avbryt

Variabeln `abort` är en boolesk variabel som kan förhindra att nästa spårningsanrop skickas till Adobe.

## Använda variabeln abort i användargränssnittet för datainsamling i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## AppMeasurement-syntax och anpassad kodredigerare i användargränssnittet för datainsamling

Variabeln `abort` är boolesk. Dess standardvärde är `false`.

* Om värdet är `true` skickar inte nästa spårningsanrop ([`t()`](../functions/t-method.md) eller [`tl()`](../functions/tl-method.md)) några data till Adobe.
* Om den är inställd på `false` eller inte är definierad händer ingenting.

```js
s.abort = true;
```

>[!NOTE]
>
>Variabeln `abort` återställs till `false` efter varje spårningsanrop. Om du behöver avbryta efterföljande spårningsanrop på samma sida anger du `abort` till `true` igen.

## Exempel

Variabeln `abort` kan anges i funktionen [`doPlugins()`](../functions/doplugins.md), som är den sista funktionen som ska köras innan en bildbegäran skickas till Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Du kan centralisera den logik som du använder för att identifiera aktiviteter som du inte vill spåra, till exempel vissa anpassade länkar eller externa länkar i visningsannonser.
