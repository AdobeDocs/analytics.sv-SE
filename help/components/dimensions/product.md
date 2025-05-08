---
title: Produkt
description: Produktens namn.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Produkt

Produktdimensionen [dimension](overview.md) rapporterar namnet på produkten i träffen. Det är användbart för implementeringar som använder variabeln `products` och som vill se mätvärden runt produkter, till exempel de främsta säljarna eller de mest visade. Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den andra delen av strängen i variabeln [`products`](/help/implement/vars/page-vars/products.md). Tecken mellan det första och andra semikolon (`;`) fyller i den här dimensionen.

## Dimension-objekt

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du skapar en konsekvent namnkonvention för produkter. [Klassificeringar](../classifications/classifications-overview.md) är tillgängliga om du vill gruppera produkter på ett annat sätt eller ange ett mer användarvänligt namn. Adobe rekommenderar att du använder både dimensionerna &quot;Produkt&quot; och &quot;Kategori&quot;.
