---
description: Beskriver hur du definierar målvalutakoder för stöd för flera valutor som ska fungera.
title: Stöd för flera valutor
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 2%

---

# Stöd för flera valutor

Adobe erbjuder flera nivåer av valutakonvertering så att organisationen kan uppnå den önskade valutan i många rapporter. Vid konvertering inträffar tre nivåer:

## Sidnivå

Du kan använda [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) variabel för att ange önskad valuta på varje sida. Om valutan på sidan inte överensstämmer med målrapportsvitens valuta, utför Adobe en valutakonvertering till rapportsvitens valuta baserat på den aktuella dagens växelkurs. Den konverterade valutan registreras.

## Rapportsvitens nivå

Varje rapportsvit har en **basvaluta**. Den här valutan anger kontexten för alla valutamått (som [Intäkter](/help/components/metrics/revenue.md)). Alla valutadata som lagras finns i rapportsvitens basvaluta.

## Användarnivå

För Rapporter och analyser kan användare ange en annan valuta än rapportsvitens basvaluta under [Rapportinställningar](/help/analyze/reports-analytics/report-settings.md). Den här inställningen är icke-förstörande, vilket innebär att den inte ändrar underliggande data. I stället tillämpas grundläggande valutakonvertering på alla rapporter som visas baserat på dagens valutakurs. Om du visar samma rapport på olika dagar kan siffrorna ändras på grund av olika dagliga valutakurser.

Analysis Workspace erbjuder för närvarande ingen valutakonvertering på användarnivå.
