---
title: Alla söksidor rankade
description: Bestäm vilken sida i en sökmotor en besökare klickade igenom till din webbplats.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Alla söksidor rankade

Med dimensionen [Alla söksidor rankade](overview.md) får du information om vilken sida av sökresultat en besökare klickade igenom på din webbplats. Om din webbplats till exempel visas på den andra sidan av sökresultatet i en sökmotor är dimensionsobjektet för den här variabeln&quot;Söksida 2&quot;.

## Fyll den här dimensionen med data

För att den här dimensionen ska fungera måste rapportsviten ha [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) korrekt konfigurerade. Den här dimensionen fylls i automatiskt i av AppMeasurement utan att några implementeringskodändringar görs.

## Dimension-objekt

Om en besökare klickar igenom till din webbplats från en sökmotor är dimensionens värde&quot;Söksida&quot; följt av det sidnummer som de klickade på. Om en träff inte kommer från en sökmotor är dimensionens värde&quot;Ospecificerat&quot;.
