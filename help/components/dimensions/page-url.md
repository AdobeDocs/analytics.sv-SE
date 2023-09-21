---
title: Sidans URL
description: Sidans URL.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# Sidans URL

Sidans URL [dimension](overview.md) listar URL:erna på din webbplats.

>[!IMPORTANT]
>
>Den här dimensionen är bara tillgänglig i Data Warehouse. Om du vill använda en URL-dimension i andra Analytics-lösningar bör du överväga att kopiera värdet till en [eVar](evar.md) på varje träff.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`g` och `-g` frågesträngar](/help/implement/validate/query-parameters.md) in [Anrop till sidvyn (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) alltid ta bort den här dimensionen, även om `g` frågesträngen finns.

Ibland är URL-adresser längre än 255 byte. AppMeasurementet använder `g` frågesträngsparameter för de första 255 byten i URL:en i bildbegäranden. Om en URL är längre än 255 byte lagras resten av URL:en i `-g` frågesträngparameter. Protokoll- och frågesträngar i URL:en ingår i den här variabeln.

AppMeasurementet samlar automatiskt in dessa data baserat på sidans URL. Du kan åsidosätta det insamlade värdet med [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabel.

## Fyll i en eVar med URL

Adobe rekommenderar att du anger eVar för den sammanfogade strängen `window.location.hostname + window.location.pathname`. Strängen fungerar vanligtvis bättre än `window.location.href` därför att protokoll, frågesträngar och ankartaggar utelämnas.

Om du vill att eVarna ska matcha sidans URL-dimension exakt i Datan Warehouse kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) och ställ in eVarna på `D=g` på varje träff.

## Dimensioner

Bland Dimensionerna finns URL-adresserna till sidorna på webbplatsen.
