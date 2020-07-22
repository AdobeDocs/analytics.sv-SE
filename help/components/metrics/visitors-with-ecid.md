---
title: Besökare med Experience Cloud ID
description: Antalet unika besökare som använder Adobe Experience Cloud ID-tjänsten.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 4%

---


# Besökare med Experience Cloud ID

Mätvärdet &quot;Besökare med Experience Cloud ID&quot; visar antalet unika besökare som identifieras av Adobe med hjälp av [Experience Cloud ID-tjänsten](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html). Den här dimensionen är användbar vid jämförelse med [unika besökarmått](unique-visitors.md) för att säkerställa att de flesta besökare på din webbplats använder ID-tjänsten. Om en stor del av besökarna inte använder ID-tjänstens cookies kan det tyda på ett problem i implementeringen.

>[!NOTE]
>
>Det här måttet är särskilt viktigt för felsökning om du använder flera Experience Cloud-tjänster, till exempel Adobe Target eller Adobe Audience Manager. Segment som delas mellan olika Experience Cloud-produkter innehåller inte besökare som saknar ett Experience Cloud-ID.

## Hur det här måttet beräknas

Det här måttet baseras på [unika besökares](unique-visitors.md) mått, förutom att det endast omfattar individer som identifieras med `mid` frågesträngen (baserat på [`s_ecid`](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-analytics.html) cookien).

## Felsök konfigurationen av ditt Experience Cloud-ID

Indikatorn &quot;Besökare med Experience Cloud-ID&quot; kan vara användbar vid felsökning av Experience Cloud-integreringar eller identifiering av områden på platsen där ID-tjänsten inte är installerad.

Jämför besökarna med Experience Cloud-ID:t genom att dra dem sida vid sida med unika besökare:

![Unik besökarjämförelse](assets/metric-mcvid1.png)

I det här exemplet ska du lägga märke till att varje sida har samma antal unika besökare som besökare med ett Experience Cloud-ID. Det totala antalet unika besökare är dock större än det totala antalet besökare med Experience Cloud ID. Du kan skapa ett [beräknat mått](../c-calcmetrics/cm-overview.md) för att ta reda på vilka sidor som inte ställer in ID-tjänsten. Du kan använda följande definition:

![Beräknad måttdefinition](assets/metric-mcvid2.png)

Genom att lägga till det beräknade måttet i rapporten kan du sortera sidrapporten så att sidor med det högsta antalet besökare utan ett MCID visas:

![Sidor utan ID-tjänst](assets/metric-mcvid3.png)

Observera att dimensionsobjektet&quot;Produktsnabbvyer&quot; inte implementeras korrekt med identitetstjänsten. Du kan samarbeta med lämpliga team inom organisationen för att uppdatera dessa sidor så snart som möjligt. Du kan skapa en liknande rapport med vilken typ av dimension som helst, till exempel [webbläsartyp](../dimensions/browser-type.md), [platsavsnitt](../dimensions/site-section.md)eller [eVar](../dimensions/evar.md).
