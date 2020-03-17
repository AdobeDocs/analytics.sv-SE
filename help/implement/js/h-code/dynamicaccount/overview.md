---
title: Översikt över dynamiska konton
description: Lär dig arbetsflödet om hur du dynamiskt väljer en rapportserie med H-kod.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# Översikt över dynamiska konton

> [!IMPORTANT] Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller Adobe Experience Platform Launch.

Dynamiska konton är en implementeringsfunktion som gör att du kan avgöra vilken rapportsvit som ska användas baserat på kriterier som du anger. Om din organisation behöver mer än en rapportserie men vill använda samma implementering mellan dina webbplatser är dynamiska konton en bra lösning.

> [!TIP] Adobe rekommenderar att du skickar data till en enda rapportserie och sedan använder virtuella rapportsviter för att separera data om det behövs. Mer information finns i avsnittet om [Global Report Suite](../../../prepare/global-rs.md) .

Tre variabler används för att dynamiskt välja en rapportserie.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Aktivera eller inaktivera dynamiskt kontoval.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Avgör vilket värde som ska observeras. Till exempel URL:en eller en frågesträng.
* [`dynamicAccountList`](dynamicaccountlist.md): Jämför värdena med `dynamicAccountMatch`, och om en matchning hittas, fyller i `account` variabeln.

Om `dynamicAccountSelection = true`värdet inom `dynamicAccountMatch` jämförs med `dynamicAccountList`. Om värdena i `dynamicAccountList` matchar varandra inkluderas rapportsvitens ID i `account` variabeln.

## Standardrapportsserie

Variabeln kan anges först och fungerar som ett standardvärde om ingen av de angivna strängarna hittas. `account` Exempel:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Om `location.hostname` varken `dev.example.com` eller `example.com`så skickas träffen till `examplersiddefault`.

## Taggar för flera programsviter

Taggar för flera programsviter kan användas med dynamiskt kontoval. Exempel:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Om `location.hostname` innehåller `example.com`det skickas träffen till både `examplersid1` och `examplersid2`.
