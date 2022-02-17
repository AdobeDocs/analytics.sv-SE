---
title: Alla söksidor rankade
description: Bestäm vilken sida i en sökmotor en besökare klickade igenom till din webbplats.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Alla söksidor rankade

Dimensionen&quot;Alla söksidor rankas&quot; ger dig insikt i vilken sida av sökresultat en besökare klickade igenom till din webbplats. Om din webbplats till exempel visas på den andra sidan av sökresultatet i en sökmotor är dimensionsobjektet för den här variabeln&quot;Söksida 2&quot;.

## Fyll den här dimensionen med data

För att få den här dimensionen att fungera måste rapportsviten ha [Interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) korrekt konfigurerad. AppMeasurement fyller automatiskt i den här dimensionen utan att några implementeringskodändringar görs.

## Dimensioner

Om en besökare klickar igenom till din webbplats från en sökmotor är dimensionens värde&quot;Söksida&quot; följt av det sidnummer som de klickade på. Om en träff inte kommer från en sökmotor är dimensionens värde&quot;Ospecificerat&quot;.
