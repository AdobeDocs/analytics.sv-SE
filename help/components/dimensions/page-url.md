---
title: Sidans URL
description: Sidans URL.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---


# Sidans URL

Dimensionen &quot;Sidadress&quot; visar URL:erna på din webbplats.

>[!IMPORTANT]
>
>Den här dimensionen är bara tillgänglig i Data warehouse. Om du vill använda en URL-dimension i andra Analytics-lösningar bör du överväga att kopiera värdet till en [eVar](evar.md) för varje träff.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`g` - och `-g` frågesträngarna](/help/implement/validate/query-parameters.md) i [sidvyanrop (`t()`)](/help/implement/vars/functions/t-method.md). [Länkspårningsanrop (`tl()`)](/help/implement/vars/functions/tl-method.md) tar alltid bort den här dimensionen, även om `g` frågesträngen finns.

Ibland är URL-adresser längre än 255 byte. AppMeasurement använder frågesträngsparametern för de första 255 byten i URL:en i bildbegäranden. `g` Om en URL är längre än 255 byte lagras resten av URL:en i `-g` frågesträngsparametern. Protokoll- och frågesträngar i URL:en ingår i den här variabeln.

AppMeasurement samlar automatiskt in dessa data baserat på sidans URL. Du kan åsidosätta det insamlade värdet med hjälp av [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabeln.

## Fylla i en eVar med URL

Adobe rekommenderar att du anger en eVar för den sammanfogade strängen `window.location.hostname + window.location.pathname`. Strängen fungerar vanligtvis bättre än `window.location.href` eftersom den inte innehåller protokoll, frågesträngar och ankartaggar.

Om du vill att eVar ska matcha sidans URL-mått exakt i Data warehouse kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) och ställa in eVar på `D=g` varje träff.

## Dimensioner

Bland Dimensionerna finns URL-adresserna till sidorna på webbplatsen.
