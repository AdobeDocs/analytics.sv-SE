---
title: Sidans URL
description: Sidans URL.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Sidans URL

Sidans URL-adress [dimension](overview.md) visar URL-adresserna på din webbplats.

>[!IMPORTANT]
>
>Den här dimensionen är bara tillgänglig i Data Warehouse. Om du vill använda en URL-dimension i andra Analytics-lösningar bör du överväga att kopiera värdet till en [eVar](evar.md) för varje träff.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`g` och `-g` frågesträngar ](/help/implement/validate/query-parameters.md) i [sidvisningsanrop (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) tar alltid bort den här dimensionen, även om frågesträngen `g` finns.

Ibland är URL-adresser längre än 255 byte. AppMeasurementet använder frågesträngsparametern `g` för de första 255 byten i URL:en i bildbegäranden. Om en URL är längre än 255 byte lagras resten av URL:en i frågesträngsparametern `-g`. Protokoll- och frågesträngar i URL:en ingår i den här variabeln.

AppMeasurementet samlar automatiskt in dessa data baserat på sidans URL. Du kan åsidosätta det insamlade värdet med variabeln [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Fyll i en eVar med URL

Adobe rekommenderar att du anger en eVar för den sammanfogade strängen `window.location.hostname + window.location.pathname`. Strängen fungerar vanligtvis bättre än `window.location.href` eftersom den inte innehåller protokoll, frågesträngar och ankartaggar.

Om du vill att eVarna ska matcha sidans URL-dimension exakt i Datan Warehouse kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) och ställa in eVarna på `D=g` för varje träff.

## Dimensioner

Bland Dimensionerna finns URL-adresserna till sidorna på webbplatsen.
