---
title: Sidans URL
description: Sidans URL.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# Sidans URL

Dimensionen &quot;Sidadress&quot; visar URL:erna på din webbplats.

>[!IMPORTANT]
>
>Den här dimensionen är bara tillgänglig i Data warehouse. Om du vill använda en URL-dimension i andra Analytics-lösningar använder du en [eVar](evar.md).

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`g` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabeln.

## Fylla i en eVar med URL

Adobe rekommenderar att du anger en eVar för den sammanfogade strängen `window.location.hostname + window.location.pathname`. Strängen fungerar vanligtvis bättre än `window.location.href` eftersom den inte innehåller protokoll, frågesträngar och ankartaggar.

Om du vill att eVar ska matcha sidans URL-mått exakt i Data warehouse kan du använda [dynamiska variabler](/help/implement/vars/page-vars/dynamic-variables.md) och ställa in eVar på `D=g` varje träff. Observera att den här metoden inte fungerar för anpassade länkträffar eftersom sidans URL rensas för alla [`tl()`](/help/implement/vars/functions/tl-method.md) anrop.

## Dimensionsvärden

Dimensionsvärdena inkluderar URL:er för sidorna på din webbplats.
