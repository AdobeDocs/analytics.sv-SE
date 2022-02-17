---
title: Besökare med Experience Cloud ID
description: Antalet unika besökare som använder Adobe Experience Cloud ID-tjänsten.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---

# Besökare med Experience Cloud ID

Mätvärdet &quot;Besökare med Experience Cloud-ID&quot; visar antalet unika besökare som identifierades av Adobe med [Experience Cloud ID-tjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html). Det här måttet är användbart att jämföra med [Unika besökare](unique-visitors.md) mätvärden för att säkerställa att de flesta besökare på webbplatsen använder ID-tjänsten. Om en stor del av besökarna inte använder ID-tjänstens cookies kan det tyda på ett problem i implementeringen.

>[!NOTE]
>
>Det här måttet är särskilt viktigt för felsökning om du använder flera Experience Cloud-tjänster, till exempel Adobe Target eller Adobe Audience Manager. Segment som delas mellan olika Experience Cloud-produkter innehåller inte besökare som saknar ett Experience Cloud-ID.

## Hur det här måttet beräknas

Det här måttet baseras på [Unika besökare](unique-visitors.md) metriska, förutom att det endast omfattar individer som identifieras med `mid` frågesträng (baserad på [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

## Felsök konfigurationen av ditt Experience Cloud-ID

Indikatorn &quot;Besökare med Experience Cloud-ID&quot; kan vara användbar vid felsökning av Experience Cloud-integreringar eller identifiering av områden på platsen där ID-tjänsten inte är installerad.

Jämför besökarna med Experience Cloud-ID:t genom att dra dem sida vid sida med unika besökare:

![Unik besökarjämförelse](assets/metric-mcvid1.png)

I det här exemplet ska du lägga märke till att varje sida har samma antal unika besökare som besökare med ett Experience Cloud-ID. Det totala antalet unika besökare är dock större än det totala antalet besökare med Experience Cloud ID. Du kan skapa en [beräknat mått](../c-calcmetrics/cm-overview.md) för att ta reda på vilka sidor som inte ställer in ID-tjänsten. Du kan använda följande definition:

![Beräknad måttdefinition](assets/metric-mcvid2.png)

Genom att lägga till det beräknade måttet i rapporten kan du sortera sidrapporten så att sidor med det högsta antalet besökare utan ett MCID visas:

![Sidor utan ID-tjänst](assets/metric-mcvid3.png)

Observera att dimensionsobjektet&quot;Produktsnabbvyer&quot; inte implementeras korrekt med identitetstjänsten. Du kan samarbeta med lämpliga team inom organisationen för att uppdatera dessa sidor så snart som möjligt. Du kan skapa en liknande rapport med alla typer av dimensioner, som [Typ av webbläsare](../dimensions/browser-type.md), [Site section](../dimensions/site-section.md)eller [eVar](../dimensions/evar.md).
