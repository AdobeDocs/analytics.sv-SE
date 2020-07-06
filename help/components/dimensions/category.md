---
title: Kategori
description: Produktkategorin för träffen.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Kategori

Dimensionen Kategori rapporterar produktkategorin för träffen. Det är användbart för implementeringar som använder variabeln och som vill se mätvärden runt produktkategorin, till exempel de främsta säljarna eller de mest visade. `products` Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den första delen av strängen i [`products`](/help/implement/vars/page-vars/products.md) variabeln. Allt före det första semikolon (`;`) fyller i den här dimensionen.

## Dimensionsvärden

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vilka dimensionsvärden som är. Adobe rekommenderar att du grupperar enskilda produkter i meningsfulla kategorier, både med dimensionerna &quot;Produkt&quot; och &quot;Kategori&quot;.

>[!TIP]
>
>I tidigare versioner av Adobe Analytics fanns det vissa begränsningar för dimensionen &quot;Kategori&quot; på grund av dess bearbetningsarkitektur. Dessa begränsningar har sedan dess tagits bort så att du kan använda alla mätvärden och eventuella fel.
