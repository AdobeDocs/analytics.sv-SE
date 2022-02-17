---
title: Översikt över dynamiska konton
description: Lär dig arbetsflödet om hur du dynamiskt väljer en rapportserie med H-kod.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 4%

---

# Översikt över dynamiska konton

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller -taggar i Adobe Experience Platform.

Dynamiska konton är en implementeringsfunktion som gör att du kan avgöra vilken rapportsvit som ska användas baserat på kriterier som du anger. Om din organisation behöver mer än en rapportserie men vill använda samma implementering mellan dina webbplatser är dynamiska konton en bra lösning.

>[!TIP]
>
>Adobe rekommenderar att du skickar data till en enda rapportserie och sedan använder virtuella rapportsviter för att separera data om det behövs. Se [Överväganden för globala rapportsviter](../../../prepare/global-rs.md) för mer information.

Tre variabler används för att dynamiskt välja en rapportserie.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Aktivera eller inaktivera dynamiskt kontoval.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Avgör vilket värde som ska observeras. Till exempel URL:en eller en frågesträng.
* [`dynamicAccountList`](dynamicaccountlist.md): Jämför värdena med `dynamicAccountMatch`, och om en matchning hittas, fyller i `account` variabel.

If `dynamicAccountSelection = true`, värdet inom `dynamicAccountMatch` jämförs med `dynamicAccountList`. Om värdena i `dynamicAccountList` matchar, så ingår rapportsvitens ID i `account` variabel.

## Standardrapportsserie

The `account` variabeln kan anges först och fungerar som ett standardvärde om ingen av de angivna strängarna hittas. Exempel:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

If `location.hostname` var ingetdera `dev.example.com` eller `example.com`, träffen skickas till `examplersiddefault`.

## Taggar för flera programsviter

Taggar för flera programsviter kan användas med dynamiskt kontoval. Exempel:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

If `location.hostname` innehåller `example.com`, skickas träffen till båda `examplersid1` och `examplersid2`.
