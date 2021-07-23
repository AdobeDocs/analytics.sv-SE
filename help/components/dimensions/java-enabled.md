---
title: Java aktiverat
description: Avgör om Java är aktiverat i webbläsaren.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Java aktiverat

Dimensionen Java enabled avgör om webbläsaren vid det tillfället har Java aktiverat. Det är praktiskt om du vill lägga in Java-baserade funktioner på webbplatsen och vill veta hur många besökare som redan har Java aktiverat. För dem som har Java inaktiverat kan du ange ett alternativ eller instruktioner för hur du aktiverar det.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v`-frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data genom att identifiera om Java är aktiverat i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern `v` som innehåller &quot;Y&quot; eller &quot;N&quot; om du vill använda den här dimensionen.

## Dimensioner

Bland Dimensionerna finns &quot;Enabled&quot;, &quot;Disabled&quot; och &quot;Unknown&quot;.

* **Aktiverad**: Java är aktiverat i webbläsaren. Frågesträngen `v` innehöll värdet Y.
* **Inaktiverad**: Java är inaktiverat i webbläsaren eller stöder inte Java på något annat sätt. Frågesträngen `v` innehöll värdet &quot;N&quot;.
* **Okänd**: AppMeasurement kunde inte identifiera Java-stöd. Frågesträngen `v` fanns inte i avbildningsbegäran.
