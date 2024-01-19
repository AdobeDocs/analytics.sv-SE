---
description: Beskriver hur du definierar målvalutakoder för stöd för flera valutor som ska fungera.
title: Stöd för flera valutor
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Stöd för flera valutor

Adobe erbjuder flera nivåer av valutakonvertering så att organisationen kan uppnå den önskade valutan i många rapporter. Vid konvertering inträffar tre nivåer:

## Sidnivå

Du kan använda [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) variabel för att ange önskad valuta på varje sida. Om valutan på sidan inte överensstämmer med målrapportsvitens valuta, utför Adobe en valutakonvertering till rapportsvitens valuta baserat på den aktuella dagens växelkurs. Den konverterade valutan registreras.

## Rapportsvitens nivå

Varje rapportsvit har en **basvaluta**. Den här valutan anger kontexten för alla valutamått (som [Intäkter](/help/components/metrics/revenue.md)). Alla valutadata som lagras finns i rapportsvitens basvaluta.

