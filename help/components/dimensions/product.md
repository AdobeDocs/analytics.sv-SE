---
title: Produkt
description: Produktens namn.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Produkt

Produktdimensionen [dimension](overview.md) rapporterar namnet på produkten i träffen. Det är användbart för implementeringar som använder variabeln `products` och som vill se mätvärden runt produkter, till exempel de främsta säljarna eller de mest visade. Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den andra delen av strängen i variabeln [`products`](/help/implement/vars/page-vars/products.md). Tecken mellan det första och andra semikolon (`;`) fyller i den här dimensionen.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du skapar en konsekvent namnkonvention för produkter. [Klassificeringar](../classifications/c-classifications.md) är tillgängliga om du vill gruppera produkter på ett annat sätt eller ange ett mer användarvänligt namn. Adobe rekommenderar att du använder både måtten &quot;Produkt&quot; och &quot;Kategori&quot;.
