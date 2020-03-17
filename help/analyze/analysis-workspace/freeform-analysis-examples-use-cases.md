---
description: Exempel på hur datatabeller, segment och användningsområden används för Analysis Workspace.
keywords: Analysis Workspace
title: Användningsexempel för Analysis Workspace
topic: Reports and analytics
uuid: 09e20b76-8c31-4d20-920b-bebc877b3b70
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Användningsexempel för Analysis Workspace

Exempel på hur datatabeller, segment och användningsområden används för Analysis Workspace.

Ni kan dirigera forskning över era data för att besvara specifika frågor och sammanställa berättelser om kundens interaktioner och målgruppsintressen. I en frihandsmiljö kan du använda mått, mätvärden och segment över en tidsperiod för att direkt hämta måldata. Skapa analyser för att anpassa efter specifika frågor och publicera sedan information i omfattande rapporter och visualiseringar som kan delas och enkelt tolkas av även den mest tidsbegränsade frontlinjeanvändaren.

![](assets/two-months-summary-project.png)

**Exempel**

* Som medieföretag kanske du vill jämföra nya besökare, återkommande besökare och de mest lojala besökarna för att se hur innehållsförbrukningen förändras över tid för varje segment.
* Jämför konverteringsgraden för märkesnyckelord och nyckelord utan varumärke.
* Dela upp sidvisningar efter intern sökning, extern sökning, landningssidor och så vidare, för att förstå varför både varumärkesprofilerade och icke-varumärkesprofilerade termer fungerar annorlunda.
* Jämför dag mot nästa dag för att jämföra kolumner eller rader för att analysera tillväxt över flera mätvärden.
* Gör en enkel fråga, till exempel studsar per dimension.

## Exempel {#section_9EFDEF038CAD4954BCFB118A8F33A96F}

Anta att du är marknadsföringsanalytiker för en återförsäljare av friluftsutrustning och att du har till uppgift att undersöka hur en Thanksgiving-kampanj nyligen har genomförts och hur du kan rekommendera hur du kan förbättra kampanjer på plats. I det här exemplet visas hur du kan jämföra kampanjintäktsdata för olika segment och lägga till uppdelningar för att gå vidare i kampanjen.

1. Välj lämplig rapportsvit.
1. Sök till exempel efter dimensionen Interna kampanjplaceringar och dra den till den vänstra delen av tabellarbetsytan (dessa data utgör tabellraderna).

   ![](assets/drag_dimension.png)

1. Klicka nu på segmentikonen längst upp till vänster och dra olika kundlojalitetssegment till höger på arbetsytan. Du kommer att jämföra segmenten med varandra direkt. Dessa utgör tabellkolumnerna.

   ![](assets/drag_segments.png)

1. Klicka på ikonen Händelser (mått) längst upp till vänster och lägg till intäktsmåttet under varje segment. Lägg märke till hur rapporten genereras automatiskt. Nu kan ni börja jämföra kampanjintäkterna för dessa kundsegment.

   ![](assets/drag_metrics.png)

1. Om du nu vill se vilka produkter som var mest effektiva i den vänstra banderollplatsen på dina sidor kan du dela upp Vänster banderoll efter produktnamn. Klicka bara på Dimensions-ikonen och dra produktnamnsdimensionen över den vänstra bannern.

   ![](assets/breakdown_prodname.png)

1. Men du kan fördjupa dig ännu mer. Man kan fråga vilka söktermer folk brukade använda för att hitta på er bästsäljande produkt, Norfolk Highland. Allt du behöver göra är att dra den interna söktermdimensionen över produktnamnet:

   ![](assets/breakdown_intsearchterm.png)

   Ett nytt uppdelningsresultat visas:

   ![](assets/breakdown_result.png)

   Ni har redan delat upp data på ett sätt som kan leda till rekommendationer och merförsäljning för era marknadsföringsteam som kan implementera dem i andra kampanjer och nå ännu större intäkter för ert företag. Du kan göra fler uppdelningar tills du får de resultat du vill ha.

   Nu kan ni [dela](/help/analyze/analysis-workspace/curate-share/curate.md) rapporten med säljarna.

