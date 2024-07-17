---
title: Kategori
description: Produktkategorin för träffen.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Kategori

Kategorin [dimension](overview.md) rapporterar produktkategorin för träffen. Det är användbart för implementeringar som använder variabeln `products` och som vill se mått runt produktkategorin, till exempel bästsäljare eller mest visade. Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den första delen av strängen i variabeln [`products`](/help/implement/vars/page-vars/products.md). Allt före det första semikolon (`;`) fyller i den här dimensionen.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du grupperar enskilda produkter i meningsfulla kategorier med hjälp av både produktdimensionerna och kategoridimensionerna.

>[!TIP]
>
>I tidigare versioner av Adobe Analytics fanns det vissa begränsningar för dimensionen &quot;Kategori&quot; på grund av dess bearbetningsarkitektur. Dessa begränsningar har sedan dess tagits bort så att du kan använda alla mätvärden och eventuella fel.
