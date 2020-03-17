---
title: Målgruppsrapporter i Adobe Analytics
description: Lär dig hur du skapar målgruppsbaserade rapporter med Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6217430bf0ae9c0f9c6426e4bb2a8101257068e7

---


# Målgruppsrapporter

Målgruppsrapporter visar information om vilka typer av personer som besöker er webbplats.

På den här sidan förutsätts att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Aktiva användare

Aktiva användare visar det kumulativa antalet användare till din webbplats under de föregående 1, 7, 14 eller 28 dagarna. Även om Adobe inte har den exakta beräkning som används i Google Analytics, kan du använda måttet Unika besökare för att se antalet användare på din webbplats som inte har duplicerats baserat på det valda datumintervallet.

Så här får du ett linjediagram över unika besökare:

1. Klicka på ikonen Visualiseringar till vänster och dra linjevisualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan måttet **Unika besökare** till det mindre området med etiketten &#39;Släpp ett mätvärde här&#39;.
3. Om du vill ha en annan granularitet drar du det önskade datumintervallet (t.ex. **Dag**, **Vecka**, **Månad** osv.) ovanpå den befintliga datumdimensionshuvudet.

Se [Unika besökare](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) i användarhandboken för komponenter för mer information om hur Adobe beräknar unika besökare.

## Livstidsvärde

Livstidsvärdet är en funktion som kräver ytterligare specialiserad implementering på båda plattformarna. Adobe rekommenderar att du samarbetar med en implementeringskonsult för att få fram dessa data.

## Kohortanalys

Kohortanalys visar hur ofta samma användare återvänder till din webbplats.

Så här skapar du en kohorttabell:

1. Klicka på visualiseringsikonen till vänster och dra CSS-visualiseringen till arbetsytan.
2. Klicka på ikonen Komponenter till vänster och dra sedan mätvärdet för **Besök** till både Inkluderingsvillkor och Returvillkor.
3. Klicka på Skapa.

Se [Kohortanalys](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) i användarhandboken för Analysis Workspace för mer information om ytterligare anpassningar av kohortvisualiseringen.

## Målgrupper

Målgruppsrapporten i Google Analytics kräver att målgrupper skapas. Publiken måste också konfigureras i Adobe via Adobe Audience Manager. Mer information finns i användarhandboken för Adobe Audience Manager.

## Användarutforskaren

Med rapporten User Explorer kan analytiker visa enskilda besök via anonyma identifierare. Adobe identifierar inte backend-ID:n utanför dataflöden, som är rådataexport på träffnivå.

* Om du vill använda dessa data i Analysis Workspace kan du arbeta med en implementeringskonsult för att skicka det anonymiserade unika identifieringsvärdet för cookie till en eVar. Observera att detta bara fungerar med mindre implementeringar som består av mindre än 1 miljon unika besökare per månad.
* Om data önskas i dataflöden är de sammanfogade kolumnerna `visid_high` och `visid_low` det vanligaste sättet att identifiera unika besökare. Läs mer om [datafeeds](/help/export/analytics-data-feed/data-feed-overview.md) i användarhandboken för Export.

## Demografiska rapporter och intresserapporter

Demografiska data och intressedata ger information om webbplatsanvändarnas ålder, kön och intressen. Dessa data samlas in av Google via deras funktioner för spårning mellan webbplatser.

Demografiska data och intressedata samlas inte in automatiskt av Adobe. Men om din organisation hämtar dessa data kan du använda kundattribut, en funktion i Adobe Experience Cloud-plattformen. Det ger fullständig kontroll över hur data ordnas efter attribut och är inte begränsat till enbart demografi eller intressen.

Mer information finns i hjälpen om kundattribut.

## Geo - språk

I geospråkrapporten visas webbplatstrafiken med språkinställningen i besökarens webbläsare.

Så här skapar du en språkrapport:

1. På menyn Komponenter letar du upp **språkdimensionen** och drar den till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [språkdimensionen](/help/components/c-variables/dimensionslist/reports-languages.md) i användarhandboken för komponenter.

## Geo - plats

Rapporten om geografisk plats ger en global kartvy där data delas upp per land.

Så här skapar du en geoplatsrapport:

1. Klicka på ikonen Visualiseringar till vänster och dra kartvisualiseringen till arbetsytan ovanför den tomma friformstabellen.
2. Klicka på ikonen Komponenter till vänster och dra sedan måttet **Unika besökare** till området med etiketten Lägg till mått.
3. Klicka på Skapa.

Om tabellen också är önskad utöver kartan:

1. På menyn Komponenter letar du upp dimensionen **Länder** och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Geosegmenteringsdimensioner](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) i användarhandboken för komponenter.

## Beteende - Nytt jämfört med Returning

Den nya rapporten kontra återskicksrapporten ger en förenklad bild av de första sessionerna (nya besök) jämfört med efterföljande sessioner (återkomstbesök).

Så här skapar du en ny rapport jämfört med en rapport om återkommande besök:

1. På komponentmenyn letar du upp segmentet **Första gången du besöker** och drar det till det stora frihandsritabellområdet med etiketten &#39;Släpp en dimension här&#39;. Observera att **förstagångsbesök** är ett segment, medan Workspace vanligtvis använder dimensioner för att representera rader.
2. Leta upp segmentet **Returbesök** och dra det över segmentradrubriken. Då läggs segmentet till som en dimension under förstagångsbesök, vilket gör det enkelt att jämföra.
3. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Om du även vill ha ett linjediagram:

1. Klicka på visualiseringsikonen till vänster och dra en linjevisualisering till arbetsytan ovanför frihandstabellen
2. Markera varje rad i friformstabellen genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac). På så sätt kan båda trenderna visas i linjevisualiseringen.
3. Klicka på den lilla runda färgade punkten i det övre vänstra hörnet av linjevisualiseringen och klicka sedan på kryssrutan Lås markering.

## Beteende - Täthet och senaste

Frekvensrapporten och rapporten för senaste besök är ungefär lika med dimensionen för **besöksnummer** på arbetsytan för analyser.

1. På komponentmenyn letar du upp dimensionen **Besök nummer** och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [dimensionen Besök Nummer](/help/components/c-variables/dimensionslist/reports-visitor-number.md) i användarhandboken för komponenter.

## Beteende - engagemang

Åtaganderapporten är ungefär densamma som **tidsåtgången per besök - paketerad** dimension.

1. På komponentmenyn letar du reda på **Time Spent per Visit - Bucketed** dimension och drar den till det stora friformstabellområdet med etiketten &#39;Drop a dimension here&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Tidsåtgång per besök](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) -dimensionen i användarhandboken för komponenter.

## Teknik - webbläsare och operativsystem

Det finns flera primära dimensioner i rapporten för webbläsare och operativsystem.

* Den primära dimensionen för **webbläsaren** är även tillgänglig som en dimension i Analysis Workspace.
* Den primära dimensionen för **operativsystemet** är också tillgänglig som en dimension i Analysis Workspace.
* Den primära dimensionen **Skärmupplösning** är tillgänglig i Analysis Workspace som dimension för **Bildskärmsupplösning** .
* Den primära dimensionen **Skärmfärger** är tillgänglig i Analysis Workspace som dimension för **färgdjup** .
* Den primära dimensionen för **Flash-versionen** är inte tillgänglig i Adobe Analytics, men dessa data kan samlas in av en eVar om det behövs.

1. På komponentmenyn letar du upp den önskade dimensionen ovan och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Se följande sidor i användarhandboken för komponenter för mer information om deras respektive dimension:

* [Webbläsare](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [Operativsystem](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [Bildskärmsupplösning](/help/components/c-variables/dimensionslist/reports-technology.md)
* [Färgdjup](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## Teknik - Nätverk

Nätverksrapporten är ungefär lika med **domändimensionen** .

1. På komponentmenyn letar du upp **domändimensionen** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Domändimensionen](/help/components/c-variables/dimensionslist/reports-domains.md) i användarhandboken för komponenter.

## Mobil - översikt

Översiktsrapporten för mobilen är ungefär densamma som dimensionen för **mobilenhetstyp** . Observera att värdet &quot;Annat&quot; motsvarar skrivbordstrafiken.

1. På komponentmenyn letar du reda på dimensionen **Mobilenhetstyp** och drar den till det stora frihandstabellområdet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Mobile Device Type](/help/components/c-variables/dimensionslist/reports-device-types.md) -dimensionen i användarhandboken för komponenter.

## Mobil - enheter

Rapporten för mobila enheter är ungefär densamma som dimensionen för **mobila enheter** .

1. På komponentmenyn letar du upp dimensionen **Mobilenhet** och drar den till det stora frihandsritbordet med etiketten &#39;Släpp en dimension här&#39;.
2. Dra de önskade måtten till arbetsytan tillsammans med det automatiskt skapade **förekomstmåttet** . Mer information om hur du får tillgång till respektive mätvärde finns i [översättningsguiden](common-metrics.md) för mätvärden.

Mer information finns i [Mobile Device](/help/components/c-variables/dimensionslist/reports-devices.md) -dimensionen i användarhandboken för komponenter.

## Egen

Anpassade rapporter definieras per implementering. Samarbeta med er organisations Analytics-administratör och/eller implementeringskonsult för att tolka dessa rapporter. Vanligtvis underhåller en organisation ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md) för att hålla reda på anpassade variabelvärden och hur de fylls i.

## Benchmarking

Tack vare analysrapporter kan ni se hur olika aspekter av era data jämfört med branschens medelvärden. Adobe delar för närvarande inte med sig av jämförelsedata mellan sina kunder.

## Användarflöde

Flödesrapporten är tillgänglig på båda plattformarna. Så här skapar du en flödesrapport:

1. Klicka på visualiseringsikonen till vänster och dra en Flow-visualisering till arbetsytan ovanför frihandstabellen
2. Leta reda på **siddimensionen** och klicka sedan på pilikonen för att visa sidvärden. Dimensionsvärden är gula.
3. Leta reda på det önskade sidvärdet som du vill börja med och dra det till utrymmet som är märkt &quot;Dimension eller item&quot; i mitten
4. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.
