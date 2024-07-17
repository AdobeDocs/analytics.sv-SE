---
title: Målgruppsrapporter i Adobe Analytics
description: Lär dig skapa målgruppsbaserade rapporter med Analysis Workspace.
feature: Third-party Integration
exl-id: 739b0c3d-3f74-41fa-a2cc-f02c17d85ce2
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 0%

---

# Målgruppsrapporter

Målgruppsrapporter visar information om vilka typer av personer som besöker er webbplats.

Den här sidan förutsätter att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics](create-report.md) om du inte redan känner till verktyget i Adobe Analytics.

## Aktiva användare

Aktiva användare visar det kumulativa antalet användare till din webbplats under de föregående 1, 7, 14 eller 28 dagarna. Även om Adobe inte har den exakta beräkning som används i Google Analytics kan du använda måttet Unika besökare för att se antalet användare som inte har duplicerats till din plats baserat på det valda datumintervallet.

Så här får du ett linjediagram över unika besökare:

1. Klicka på ikonen Visualiseringar till vänster och dra linjevisualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan måttet **Unika besökare** till det mindre området med namnet &#39;Släpp ett mätvärde här&#39;.
3. Om du vill ha en annan granularitet drar du det önskade datumintervallet (t.ex. **Dag**, **Vecka**, **Månad** osv.) ovanpå den befintliga datumdimensionshuvudet.

Se [Unika besökare](/help/components/metrics/unique-visitors.md) i användarhandboken för komponenter för mer information om hur Adobe beräknar unika besökare.

## Livstidsvärde

Livstidsvärdet är en funktion som kräver ytterligare specialiserad implementering på båda plattformarna. Adobe rekommenderar att ni samarbetar med en implementeringskonsult för att få fram dessa data.

## Kohortanalys

Kohortanalys visar hur ofta samma användare återvänder till din webbplats.

Så här skapar du en kohorttabell:

1. Klicka på visualiseringsikonen till vänster och dra CSS-visualiseringen till arbetsytan.
2. Klicka på ikonen Komponenter till vänster och dra sedan måttet **Besök** till både Inkluderingsvillkor och Returvillkor.
3. Klicka på Skapa.

Se [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) i användarhandboken för Analysis Workspace för mer information om ytterligare anpassningar av kohortvisualiseringen.

## Målgrupper

Målgruppsrapporten i Google Analytics kräver att man skapar målgrupper. Publiken måste också konfigureras i Adobe via Adobe Audience Manager. Mer information finns i användarhandboken för Adobe Audience Manager.

## Användare

Med rapporten User Explorer kan analytiker visa enskilda besök via anonyma identifierare. Adobe tar inte upp backend-identifierare utanför dataflöden, som är rådataexport på träffnivå.

* Om du vill ha dessa data i Analysis Workspace kan du samarbeta med en implementeringskonsult för att skicka det anonyma unika identifieringscookie-värdet till en eVar. Observera att detta bara fungerar med mindre implementeringar som består av mindre än 1 miljon unika besökare per månad.
* Om du vill använda dessa data i dataflöden är de sammanfogade kolumnerna `visid_high` och `visid_low` det vanligaste sättet att identifiera unika besökare. Läs mer om [Datafeeds](/help/export/analytics-data-feed/data-feed-overview.md) i användarhandboken för Exportera.

## Demografiska rapporter och intresserapporter

Demografiska data och intressedata ger information om webbplatsanvändarnas ålder, kön och intressen. Dessa data samlas in av Google via deras funktioner för spårning över flera webbplatser.

Demografiska data och intressedata samlas inte in automatiskt av Adobe. Men om er organisation får dessa data kan ni använda kundattribut, en funktion inom Adobe Experience Cloud Platform. Det ger fullständig kontroll över hur data ordnas efter attribut och är inte begränsat till enbart demografi eller intressen.

Mer information finns i hjälpen för kundattribut.

## Geo - språk

I geospråkrapporten visas webbplatstrafiken med språkinställningen i besökarens webbläsare.

Så här skapar du en språkrapport:

1. Leta reda på dimensionen **Språk** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Språk](/help/components/dimensions/language.md) i användarhandboken för komponenter.

## Geo - plats

Rapporten om geografisk plats ger en global kartvy där data delas upp per land.

Så här skapar du en geoplatsrapport:

1. Klicka på ikonen Visualiseringar till vänster och dra kartvisualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan måttet **Unika besökare** till området med etiketten Lägg till mått.
3. Klicka på Skapa.

Om tabellen också är önskad utöver kartan:

1. På menyn Komponenter letar du upp dimensionen **Länder** och drar den till det stora friformstabellområdet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i måtten för [Länder](/help/components/dimensions/countries.md) i användarhandboken för komponenter.

## Beteende - Nytt jämfört med Returning

Den nya rapporten kontra återskicksrapporten ger en förenklad bild av de första sessionerna (nya besök) jämfört med efterföljande sessioner (återvändandebesök).

Så här skapar du en ny rapport jämfört med en rapport om återkommande besök:

1. På komponentmenyn letar du reda på segmentet **Första gången du besöker** och drar det till det stora frihandstabellområdet med etiketten &#39;Släpp en Dimension här&#39;. Observera att **förstagångsbesök** är ett segment, medan Workspace vanligtvis använder dimensioner för att representera rader.
2. Leta reda på segmentet **Returbesök** och dra det över segmentradrubriken. Då läggs segmentet till som en dimension under förstagångsbesök, vilket gör det enkelt att jämföra.
3. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Om du även vill ha ett linjediagram:

1. Klicka på visualiseringsikonen till vänster och dra en linjevisualisering till arbetsytan ovanför frihandstabellen
2. Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på varje rad i friformstabellen för att markera dem. På så sätt kan båda trenderna visas i linjevisualiseringen.
3. Klicka på den lilla runda färgade punkten i det övre vänstra hörnet av linjevisualiseringen och klicka sedan på kryssrutan Lås markering.

## Beteende - Täthet och senaste

Frekvensrapporten och rapporten om senaste besök är ungefär lika med dimensionen **Besök nummer** i Analysis Workspace.

1. På komponentmenyn letar du reda på dimensionen **Besök nummer** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Besök Nummer](/help/components/dimensions/visit-number.md) i användarhandboken för komponenter.

## Beteende - engagemang

Åtaganderapporten är ungefär lika med dimensionen **Tid per besök - Bucketed**.

1. På komponentmenyn letar du reda på dimensionen **Tid per besök - Bucketed** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Tid per besök](/help/components/dimensions/time-spent-per-visit.md) i användarhandboken för komponenter.

## Teknik - webbläsare och operativsystem

Det finns flera primära dimensioner i rapporten för webbläsare och operativsystem.

* Den primära dimensionen **Webbläsare** är även tillgänglig i Analysis Workspace som en dimension.
* Den primära dimensionen för **operativsystemet** är även tillgänglig i Analysis Workspace som en dimension.
* Den primära dimensionen **Skärmupplösning** är tillgänglig i Analysis Workspace som dimension **Bildskärmsupplösning**.
* Den primära dimensionen **Skärmfärger** är tillgänglig i Analysis Workspace som dimensionen **Färgdjup** .
* Den primära dimensionen **Flash version** är inte tillgänglig i Adobe Analytics, men den här informationen kan samlas in av en eVar om det behövs.

1. På komponentmenyn letar du upp den önskade dimensionen ovan och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Se följande sidor i användarhandboken för komponenter för mer information om deras respektive dimension:

* [Webbläsare](/help/components/dimensions/browser.md)
* [Operativsystem](/help/components/dimensions/operating-systems.md)
* [Bildskärmsupplösning](/help/components/dimensions/monitor-resolution.md)
* [Färgdjup](/help/components/dimensions/color-depth.md)

## Teknik - Nätverk

Nätverksrapporten är ungefär lika med dimensionen **Domän**.

1. Leta reda på dimensionen **Domän** på komponentmenyn och dra den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Domän](/help/components/dimensions/domain.md) i användarhandboken för komponenter.

## Mobil - översikt

Översiktsrapporten för mobilen är ungefär lika med dimensionen **Mobilenhetstyp** . Observera att värdet &quot;Annat&quot; motsvarar skrivbordstrafiken.

1. På komponentmenyn letar du reda på dimensionen **Mobile Device Type** och drar den till det stora frihandstabellområdet med etiketten &#39;Drop a dimension here&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Mobile device type](/help/components/dimensions/mobile-dimensions.md) i användarhandboken för komponenter.

## Mobil - enheter

Rapporten för mobila enheter är ungefär lika med dimensionen **Mobile Device** .

1. På komponentmenyn letar du reda på dimensionen **Mobile Device** och drar den till det stora frihandstabellområdet med etiketten &#39;Drop a dimension here&#39;.
2. Dra de önskade måtten till arbetsytan bredvid det automatiskt skapade **förekomstmåttet** . Mer information om hur du hämtar respektive mätvärde finns i [måttöversättningsguiden](common-metrics.md).

Mer information finns i dimensionen [Mobile device](/help/components/dimensions/mobile-dimensions.md) i användarhandboken för komponenter.

## Anpassad

Anpassade rapporter definieras per implementering. Samarbeta med er organisations Analytics-administratör och/eller implementeringskonsult för att tolka dessa rapporter. Vanligtvis har en organisation ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) som håller reda på anpassade variabelvärden och hur de fylls i.

## Benchmarking

Tack vare analysrapporter kan ni se hur olika aspekter av era data jämfört med branschens medelvärden. Adobe delar för närvarande inte med sig av jämförelsedata mellan sina kunder.

## Användarflöde

Flödesrapporten är tillgänglig på båda plattformarna. Så här skapar du en flödesrapport:

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Leta reda på dimensionen **Sidor** och klicka sedan på pilikonen för att visa sidvärden. Dimensioner är gulfärgade.
3. Leta reda på det sidvärde du vill börja med och dra det till utrymmet&quot;Dimension or item&quot; i mitten
4. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.
