---
title: Produkt
description: Produktens namn.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Produkt

Dimensionen Produkt rapporterar namnet på produkten i träffen. Det är användbart för implementeringar som använder variabeln och som vill se mätvärden runt produkter, till exempel de främsta säljarna eller de mest visade. `products` Den här dimensionen kan vara tom om du inte har några produkter på din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen refererar till den andra delen av strängen i [`products`](/help/implement/vars/page-vars/products.md) variabeln. Tecken mellan det första och andra semikolon (`;`) fyller i den här dimensionen.

## Dimensionsobjekt

Eftersom den här variabeln baseras på en anpassad sträng i implementeringen avgör organisationen vad dimensionsobjekten är. Adobe rekommenderar att du skapar en enhetlig namnkonvention för produkter. [Klassificeringar](../c-classifications2/c-classifications.md) är tillgängliga om du vill gruppera produkter på ett annat sätt eller ange ett mer användarvänligt namn. Adobe rekommenderar att du använder både dimensionerna &quot;Produkt&quot; och &quot;Kategori&quot;.
