---
title: Sidans URL
description: Sidans URL.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# Sidans URL

Dimensionen &quot;Sidadress&quot; visar URL:erna på din webbplats.

>[!IMPORTANT]
>
>Den här dimensionen är bara tillgänglig i Data warehouse. Om du vill använda en URL-dimension i andra Analytics-lösningar bör du överväga att kopiera värdet till en [eVar](evar.md) på varje träff.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`g` och `-g` frågesträngar](/help/implement/validate/query-parameters.md) in [Anrop till sidvyn (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) alltid ta bort den här dimensionen, även om `g` frågesträngen finns.

Ibland är URL-adresser längre än 255 byte. AppMeasurement använder `g` frågesträngsparameter för de första 255 byten i URL:en i bildbegäranden. Om en URL är längre än 255 byte lagras resten av URL:en i `-g` frågesträngsparameter. Protokoll- och frågesträngar i URL:en ingår i den här variabeln.

AppMeasurement samlar automatiskt in dessa data baserat på sidans URL. Du kan åsidosätta det insamlade värdet med [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabel.

## Fylla i en eVar med URL

Adobe rekommenderar att du anger en eVar för den sammanfogade strängen `window.location.hostname + window.location.pathname`. Strängen fungerar vanligtvis bättre än `window.location.href` därför att protokoll, frågesträngar och ankartaggar utelämnas.

Om du vill att eVar ska matcha sidans URL-mått exakt i Data warehouse kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) och ange eVar till `D=g` på varje träff.

## Dimensioner

Bland Dimensionerna finns URL-adresserna till sidorna på webbplatsen.
