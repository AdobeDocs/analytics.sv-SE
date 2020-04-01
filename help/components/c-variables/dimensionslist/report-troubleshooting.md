---
description: Med Adobe Analytics får ni ett flexibelt rapporteringsgränssnitt som gör att ni kan generera olika komplexa rapporter. De flesta rapporter genereras mycket snabbt, men du kan stöta på rapporter som timeout eller misslyckas med att generera. För att undvika fel vid rapportgenerering beskrivs många faktorer som påverkar rapportgenereringshastigheten. Genom att förstå den här informationen kan du strukturera rapporter så att de lättare kan genereras.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Rapportera bästa praxis och felsökning
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: dca5bac72a2cf5f5ded5072e1867676392a7850e

---


# Rapportera bästa praxis och felsökning

Med Adobe Analytics får ni ett flexibelt rapporteringsgränssnitt som gör att ni kan generera olika komplexa rapporter. De flesta rapporter genereras mycket snabbt, men du kan stöta på rapporter som timeout eller misslyckas med att generera. För att undvika fel vid rapportgenerering beskrivs många faktorer som påverkar rapportgenereringshastigheten. Genom att förstå den här informationen kan du strukturera rapporter så att de lättare kan genereras.

>[!Note]
>Dessa rekommendationer gäller Rapporter och analys, Ad hoc-analys och Report Builder.
>De gäller inte för Analysis Workspace, som har en egen uppsättning [metodtips](/help/analyze/analysis-workspace/workspace-faqs/optimizing-performance.md). De gäller inte heller >för [bästa praxis](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html)för datalager. Ytterligare en uppsättning
>[bästa praxis](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) finns för Adobe Analytics Reporting API.

## Timeout för rapport och begärandekö {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Timeout**

En enda rapport delas upp i flera begäranden (en per uppdelning) och varje begäran omfattas av en enskild tidsgräns. Schemalagda rapporter tilldelas längre tidsgränser och är mer framgångsrika än rapporter som genereras direkt i ett användargränssnitt.

**Report Suite-kö**

Varje rapportsvit har en separat kö med förfrågningar. Om många rapporter begärs samtidigt, även från olika användare, genereras ett litet antal rapporter samtidigt. När rapporterna är klara genereras återstående rapporter i den ordning som de togs emot. Om det redan finns ett stort antal komplexa rapporter i rapportsvitkön kan det leda till att en rapport som genereras snabbt tar slut.

## Faktorer som påverkar rapporthastigheten {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

Följande faktorer bidrar till längre rapportgenereringstider. Om du ökar en av dessa faktorer kan det leda till att rapporten inte får någon tidsgräns, men det kan fördröja andra rapporter i rapportsvitskön och leda till att en efterföljande rapport får en tidsgräns.

**Tidsintervall för rapportering**

Den största faktorn som påverkar rapportgenereringstiden är antalet månader som efterfrågas. Att minska antalet månader från tre till ett minskar genereringstiden avsevärt, men att minska tidsintervallet från en månad till en vecka har inte någon större effekt på rapportgenereringstiden.

**Antal mätvärden**

När antalet mätvärden ökar ökar, ökar rapportens körtid. När du tar bort mätvärden tar det ofta längre tid att generera rapporter.

**Antal uppdelningar**

I en rapport representerar varje uppdelning en separat begäran. Även om enskilda förfrågningar kan slutföras snabbt, kan tusentals uppdelningar i en enda rapport göra rapportgenereringstiden avsevärt långsammare och påverka rapportsvitens kö.

**Segmentkomplexitet**

Segment som beaktar många dimensioner eller har många (24+) regler ökar bearbetningens påverkan och ökar tiden för rapportgenerering.

**Antal unika värden**

Rapporter som innehåller hundratusentals unika värden genererar långsammare än rapporter som innehåller färre unika värden, även om segmentet eller filtret minskar antalet värden som slutligen visas i en rapport. En rapport som till exempel visar söktermer genererar vanligtvis långsammare än andra rapporter, även om ett filter används för att bara visa söktermer som innehåller ett visst värde.

## Andra rapporteringsalternativ {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Förutom att minska tidsintervallet, antalet mätvärden och antalet uppdelningar i en rapport kan följande riktlinjer bidra till att öka tillförlitligheten i rapportleveransen:

* Använd datalagret för att begära rapporter som innehåller många uppdelningar eller mätvärden. Datalagret är utformat för att generera dessa typer av rapporter.
* Schemalägg rapporter som ska köras under icke-toppvärdestimmar. Detta ökar sannolikheten för att en rapport returneras eftersom begärandekön för en rapportsvit troligtvis är tom under den tiden.
* Report Builder kan användas för att dela upp rapporter i mindre tidsintervall och förfrågningar som innehåller färre mått. Du kan sedan använda den inbyggda Excel-funktionen för att sammanfoga data från olika förfrågningar i en enda rapport.

