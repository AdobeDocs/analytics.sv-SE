---
description: Integrering med appFigures används ofta för att samla in data för flera program i flera appbutiker. Du kan skapa segment för att isolera rapportdata för en viss app- eller appbutik.
title: Segmentera appdata
uuid: 9c2aaf0d-088f-4178-8ed1-a8124087a683
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Segmentera appdata{#segmenting-app-data}

Integrering med appFigures används ofta för att samla in data för flera program i flera appbutiker. Du kan skapa segment för att isolera rapportdata för en viss app- eller appbutik.

Riktlinjer för segmentering av appFigures-data:

* Endast sidvisningsbehållare måste användas.
* Endast [AppFigures-dimensioner](/help/import/data-connectors/appfigures-overview/appfigures-metrics.md) får användas i filtreringsregler.
* Kan använda flera segmentregler så länge endast [AppFigures-dimensioner](/help/import/data-connectors/appfigures-overview/appfigures-segment-filter.md) refereras.
* Kan använda både arbetsytan Inkludera och Uteslut.
* Segmenten gäller endast Adobe Analytics v15.
