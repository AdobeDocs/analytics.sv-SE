---
description: Använd utfallsvisualisering i ett Workspace-projekt.
title: Översikt över utfall
uuid: 2d98899e-e401-4d7a-8af0-de0002f84178
feature: Visualiseringar
role: Business Practitioner, Administrator
exl-id: 85d0c88e-d159-4870-aaf6-51899d87ff77
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 2%

---

# Översikt över utfall

Utfallsvisualiseringar ger fler alternativ för att skapa utfallsrapporter. Utfallsrapporter visar var besökarna lämnade (föll ned) och fortsatte igenom (föll igenom) en fördefinierad sidsekvens.

Med hjälp av bortfallsvisualiseringar kan du

* Jämför två olika segment sida vid sida i samma rapport.
* Dra, släpp och ordna om steg i tratten (kontaktytor)
* Mixa och matcha värden från olika dimensioner och mätvärden
* Skapa en flerdimensionell utfallsrapport
* Identifiera var kunderna hamnar direkt efter att de faller bort

Utfall visar konverterings- och utfallsfrekvenser mellan varje steg eller kontaktyta i en sekvens.

Du kan till exempel spåra en besökares utfallspunkter under en inköpsprocess. Välj bara en första kontaktyta och en avslutande kontaktyta och lägg till mellanliggande kontaktytor för att skapa en navigeringsväg för webbplatsen. Men du kan också göra flerdimensionella utfall.

En bortfallsvisualisering är användbar vid analys av:

* Konverteringsgrader genom specifika processer på er webbplats (t.ex. ett inköp eller en registreringsprocess).
* Allmänna, bredare trafikflöden: Av de personer som såg hemsidan visar det här flödet hur många som har gjort en sökning och sedan hur många som till slut gick vidare för att titta på ett visst objekt.
* Korrelationer mellan händelser på din webbplats. Korrelationer visar hur många procent av dem som tittade på din integritetspolicy fortsatte att köpa en produkt.

[Videosjälvstudievideo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html)  för bortfallsvisualisering (4:15)

## Segmentering som grund för flöde och utfall {#section_654F37A398C24DDDB1552A543EE29AA9}

Segment som tillämpas på arbetsytepaneler fungerar något annorlunda än segment som tillämpas på bortfalls- och flödesrapporter i rapporter och analyser. Oftast ger de exakt samma resultat. Den största skillnaden är att Rapporter och analyser använder segmentet vid varje steg i sekvensen. Detta kan ge något annorlunda resultat.

Låt oss ta ett exempel på bortfallet med två steg:

![](assets/fallout_segments1.png)

Om du sedan använder ett segment på arbetsytans panelnivå kombineras segmentet med utfallet så här:

![](assets/fallout_seg.png)

När Rapporter och analyser däremot beräknar segmentet kombineras segmentet på det här sättet:

![](assets/fallout_segments3.png)

Rapporter och analyser kombinerar segmentet med varje steg. När behållarna är på samma nivå som utfallet (t.ex. besök eller besöksnivå) kommer detta att resultera i matchning av antalet besök eller besökare.

Om segmentet som används på panelen är mindre än utfallsnivån (t.ex. träffnivå) visas dock olika resultat på grund av hur det kombineras av rapporten. I de flesta fall matchar siffrorna i Analysis Workspace siffrorna i Rapporter och analyser. De **matchar inte** bara om alla fall nedan är sanna:

* Segmentet är inte på samma nivå som utfallet.
* Segmentet har en variabel där besökaren/besöket kan ha flera värden under ett besök/en besökare.

I de sällsynta fall där du behöver ha Analysis Workspace som matchar metoden Rapporter och analyser för att tillämpa segment på bortfall/flöde, släpper du bara segmentet i varje utfallssteg i Workspace och ger samma antal.
