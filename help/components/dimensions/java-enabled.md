---
title: Java aktiverat
description: Avgör om Java är aktiverat i webbläsaren.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Java aktiverat

&#39;Java enabled&#39; [dimension](overview.md) Anger om Java är aktiverat i webbläsaren vid den tidpunkten. Det är praktiskt om du vill lägga in Java-baserade funktioner på webbplatsen och vill veta hur många besökare som redan har Java aktiverat. För dem som har Java inaktiverat kan du ange ett alternativ eller instruktioner för hur du aktiverar det.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data genom att identifiera om Java är aktiverat i webbläsaren. Om du använder ett AppMeasurementen bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt. Om du använder en datainsamlingsmetod utanför AppMeasurementet (till exempel via API:t) måste du ta med `v` frågesträngsparameter som innehåller &quot;Y&quot; eller &quot;N&quot; om du vill använda den här dimensionen.

## Dimensioner

Bland Dimensionerna finns &quot;Enabled&quot;, &quot;Disabled&quot; och &quot;Unknown&quot;.

* **Aktiverad**: Java är aktiverat i webbläsaren. The `v` frågesträngen innehöll värdet &quot;Y&quot;.
* **Handikappade**: Java är inaktiverat i webbläsaren eller stöder inte Java på något annat sätt. The `v` frågesträngen innehöll värdet &quot;N&quot;.
* **Okänd**: AppMeasurementet kunde inte fastställa Java-stöd. The `v` frågesträngen fanns inte i bildbegäran.
