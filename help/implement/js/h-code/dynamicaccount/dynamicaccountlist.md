---
title: dynamicAccountList
description: Upprätta logik för hur implementeringen avgör dess rapportserie.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>Dynamiska konton stöds bara med äldre JavaScript-implementeringar (H-kod). Dessa variabler stöds inte i aktuella AppMeasurement-bibliotek eller i användargränssnittet för datainsamling.

The `s.dynamicAccountList` variabeln bestämmer dynamiskt värdet för `s_account`. If `dynamicAccountSelection` är inställd på `true`, `dynamicAccountMatch` variabeln jämförs med `dynamicAccountList`. Om en matchning hittas används det matchande rapportsvitens ID.

## Syntax

Variabeln är en sträng som automatiskt tolkas av JavaScript-filen.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Giltiga indata är en semikolonavgränsad lista med paren rsid och value. Varje lista innehåller följande objekt:

* Ett eller flera rapportsvit-ID:n (avgränsade med kommatecken)
* Ett likhetstecken
* En eller flera strängar som ska matchas (avgränsade med kommatecken)

Endast ASCII-standardtecken ska användas i strängen. Använd inte blanksteg.

## Exempel

För alla följande exempel är sidans URL `https://example.com/path2/?prod_id=12345`, `dynamicAccountSelection` variabeln är inställd på `true`och `s_account` variabeln är inställd på `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Pitfalls, frågor och tips

* Reglerna som anges i den här variabeln används i ordningen vänster till höger. Om `dynamicAccountMatch` variabeln matchar mer än en regel, används regeln längst till vänster för att bestämma rapportsviten. Därför placerar du mer allmänna regler till höger om listan.
* Om inga regler matchar, är standardrapportsviten i `s_account` används.
* Om sidan sparas på någons hårddisk eller översätts via en webbaserad översättningsmotor (som Google översatta sidor), kommer det dynamiska kontovalet troligtvis inte att fungera.
* The `dynamicAccountSelection` gäller endast för den del av URL:en som anges i `dynamicAccountMatch`.
* Använd [!DNL Adobe Experience Cloud Debugger] för att testa målrapportsviten.
