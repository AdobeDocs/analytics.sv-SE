---
description: Visar procentandelen besök som innehåller en enda träff.
title: Studsfrekvens
topic: Metrics
uuid: 9a5aba33-c16a-47db-b8d3-f66be6eb65be
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Studsfrekvens

Visar procentandelen besök som innehåller en enda träff.

Studsfrekvensen använder [studentmåttet](/help/components/c-variables/c-metrics/metrics-bounces.md) och beräknas som:

`Bounces divided by Entries`

Studsfrekvensen omfattar inte besök där flera åtgärder har utförts på en sida. Ett besök med en videovy på en sida är till exempel en enskild åtkomst men inte en studs.

>[!NOTE] Befintliga implementeringar kan ibland innehålla ett beräknat mått som skiljer sig från standardmåttet för Analytics. Kontrollera den beräknade måttdefinitionen för att se till att det inte finns några skillnader.

Mer information finns i den här [kunskapsbasartikeln](https://helpx.adobe.com/analytics/kb/comparing-bounces-and-single-access.html) .
