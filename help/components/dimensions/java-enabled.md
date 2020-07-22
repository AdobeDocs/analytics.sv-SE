---
title: Java aktiverat
description: Avgör om Java är aktiverat i webbläsaren.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---


# Java aktiverat

Dimensionen Java enabled avgör om webbläsaren vid det tillfället har Java aktiverat. Det är praktiskt om du vill lägga in Java-baserade funktioner på webbplatsen och vill veta hur många besökare som redan har Java aktiverat. För dem som har Java inaktiverat kan du ange ett alternativ eller instruktioner för hur du aktiverar det.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data genom att identifiera om Java är aktiverat i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern som innehåller &quot;Y&quot; eller &quot;N&quot; om du vill använda den här dimensionen. `v`

## Dimensionsobjekt

Dimensionsobjekten är Aktiverad, Inaktiverad och Okänd.

* **Aktiverad**: Java är aktiverat i webbläsaren. Frågesträngen innehöll `v` värdet &quot;Y&quot;.
* **Inaktiverad**: Java är inaktiverat i webbläsaren eller stöder inte Java på något annat sätt. Frågesträngen innehöll `v` värdet &quot;N&quot;.
* **Okänd**: AppMeasurement kunde inte identifiera Java-stöd. Frågesträngen fanns inte i bildbegäran `v` .
