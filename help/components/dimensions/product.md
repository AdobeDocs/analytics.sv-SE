---
title: Produkt
description: Produktens namn.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Produkt

Dimensionen Produkt rapporterar namnet på produkten i träffen. Det är användbart för implementeringar som använder variabeln och som vill se mätvärden runt produkter, till exempel de främsta säljarna eller de mest visade. `products` Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den andra delen av strängen i [`products`](/help/implement/vars/page-vars/products.md) variabeln. Tecken mellan det första och andra semikolon (`;`) fyller i den här dimensionen.

## Dimensioner

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du skapar en konsekvent namnkonvention för produkter. [Klassificeringar](../classifications/c-classifications.md) är tillgängliga om du vill gruppera produkter på ett annat sätt eller ange ett mer användarvänligt namn. Adobe rekommenderar att du använder både måtten &quot;Produkt&quot; och &quot;Kategori&quot;.
