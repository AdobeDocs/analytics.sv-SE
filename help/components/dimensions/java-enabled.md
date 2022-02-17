---
title: Java aktiverat
description: Avgör om Java är aktiverat i webbläsaren.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Java aktiverat

Dimensionen Java enabled avgör om webbläsaren vid det tillfället har Java aktiverat. Det är praktiskt om du vill lägga in Java-baserade funktioner på webbplatsen och vill veta hur många besökare som redan har Java aktiverat. För dem som har Java inaktiverat kan du ange ett alternativ eller instruktioner för hur du aktiverar det.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data genom att identifiera om Java är aktiverat i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med `v` frågesträngsparameter som innehåller &quot;Y&quot; eller &quot;N&quot; om du vill använda den här dimensionen.

## Dimensioner

Bland Dimensionerna finns &quot;Enabled&quot;, &quot;Disabled&quot; och &quot;Unknown&quot;.

* **Aktiverad**: Java är aktiverat i webbläsaren. The `v` frågesträngen innehöll värdet &quot;Y&quot;.
* **Handikappade**: Java är inaktiverat i webbläsaren eller stöder inte Java på något annat sätt. The `v` frågesträngen innehöll värdet &quot;N&quot;.
* **Okänd**: AppMeasurement kunde inte identifiera Java-stöd. The `v` frågesträngen fanns inte i bildbegäran.
