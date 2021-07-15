---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
source-git-commit: e7bfb56b63a9134728360c91f3c835da1952fa5a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# Merchandising eVars and Product Finding Methods

I det här dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars-variabler. Det förklarar också hur eVars marknadsförs relaterar till metoder för produktsökning.

Även om de flesta webbplatser för detaljhandeln har många sätt att hitta produkter anser Adobe att följande är de grundläggande metoder för produktupptäckt som alla kunder inom detaljhandeln bör följa i Adobe Analytics:

* Interna söknyckelord
* Interna koder för kampanjspårning
* Marknadsföring/bläddringskategorier
* Merförsäljning

I det här dokumentet kan vi mappa några eVars till lösningarna enligt följande:

* eVar2: Interna söknyckelord
* eVar3: Interna koder för kampanjspårning
* eVar4: Marknadsföring/bläddringskategorier
* eVar5: Korsförsäljning

Vi kan använda en extra eVar för att mäta prestandan för alla produktsökningsmetoder i förhållande till varandra. Förutom de sökmetoder som beskrivs ovan kommer eVar att inkludera andra sökmetoder, t.ex. länkar till produktinformationssidor från externa webbplatser, i sin jämförelse.

* eVar1: Metoder för produktsökning

Du bör inte konfigurera någon av dessa variabler som standard-eVars, utan i stället konfigurera dem så att de marknadsför eVars.  Med hjälp av eVars kan du tilldela alla framgångsrika aktiviteter till värden som hämtas av eVars på *per-product*-nivå i stället för på *per-visit/per-order*-nivå. Jag kommer att klargöra skillnaden mellan fördelningen per produkt och per order under resten av detta dokument.

För att visa hur dessa variabler ska ställas in börjar jag med ett exempel där en besökare bestämmer sig för att använda den interna sökningen &quot;sandaler&quot; för att hitta en produkt på webbplatsen.  På sidan med sökresultat för nyckelord måste du hämta in data i minst två eVars:

* `eVar2` kommer att vara lika med nyckelordet som användes i sökningen (&quot;sandaler&quot;)
* `eVar1` kommer att vara lika med den produktsökningsmetod som används (&quot;intern nyckelordssökning&quot;).

När du ställer in dessa två variabler som är lika med dessa specifika värden, vet du att besökaren använder det interna nyckelordssökordet för&quot;sandaler&quot; för att hitta en produkt.
Samtidigt vet du att besökaren inte använder de andra produktsökningsmetoderna för att hitta produkter (besökaren bläddrar t.ex. inte igenom produktkategorier exakt samtidigt som han/hon gör en nyckelordssökning). För att säkerställa att rätt tilldelning sker per produkt bör dessa oanvända metoder inte tillskriva någon kredit för att hitta en produkt som hittats via en intern nyckelordssökning.  Du måste därför infoga logik i koden (t.ex. AppMeasurement, AEP Web SDK) som automatiskt ställer in de eVars som är associerade med dessa andra sökmetoder som är lika med ett icke-sökmetod-värde.

När en användare t.ex. söker efter produkter med nyckelordet&quot;sandals&quot;, ska Analytics-kodens logik ange de variabler som är lika med följande på den interna sökresultatsidan för nyckelord:

* eVar2=&quot;sandaler&quot;: nyckelordet&quot;sandals&quot; användes i den interna nyckelordssökningen
* eVar1=&quot;intern nyckelordssökning&quot;: sökmetoden&quot;internal keyword search&quot; användes
* eVar3=&quot;icke-intern kampanj&quot;: en intern kampanj användes inte för att komma åt sökresultatsidan
* eVar4=&quot;ej webbläsare&quot;: det gick inte att komma åt en bläddringskategori på sökresultatsidan
* eVar5=&quot;ej korsförsäljning&quot;: det gick inte att klicka på en korsförsäljningslänk på sökresultatsidan

