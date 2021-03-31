---
title: Rapportera bästa praxis och felsökning
description: Bästa tillvägagångssätt och felsökningstips när du skapar rapporter.
keywords: bästa praxis;fel;timeout;felsökning;långsam
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Rapportera bästa praxis och felsökning

*Den här hjälpsidan hänvisar till bästa praxis för rapporter och analyser. För Analysis Workspace, se [Optimera Analysis Workspace-prestanda](../analysis-workspace/workspace-faq/optimizing-performance.md). Mer information om Data warehouse finns i [Bästa praxis för Data warehouse](/help/export/data-warehouse/data-warehouse-bp.md).*

Adobe Analytics har ett flexibelt rapporteringsgränssnitt med vilket man kan generera olika komplexa rapporter. De flesta rapporter genereras mycket snabbt, men du kan stöta på rapporter som timeout eller misslyckas med att generera. På den här sidan förklaras faktorer som påverkar rapportgenereringshastigheten. Genom att förstå den här informationen kan du strukturera rapporter så att de lättare kan genereras.

## Rapporttimeout och begärandekö

* **Timeout**: En enda rapport delas upp i flera begäranden (en per uppdelning) och varje begäran omfattas av en enskild tidsgräns. Schemalagda rapporter tilldelas längre tidsgränser och är mer framgångsrika än rapporter som genereras direkt i ett användargränssnitt.
* **Report Suite-kö**: Varje rapportsvit har en separat kö med förfrågningar. Om många rapporter begärs samtidigt, även från olika användare, genereras ett litet antal rapporter samtidigt. När rapporterna är klara genereras återstående rapporter i den ordning som de togs emot. Om det redan finns ett stort antal komplexa rapporter i rapportsvitkön kan det leda till att en rapport som genereras snabbt tar slut.

## Faktorer som påverkar rapportens hastighet

Följande faktorer bidrar till längre rapportgenereringstider. Om du ökar en av dessa faktorer påverkar det vanligtvis inte prestandan, men det kan fördröja andra rapporter i rapportsvitkön och orsaka att en efterföljande rapport blir timeout.

* **Tidsintervall för** rapportering: Den största faktorn som påverkar rapportgenereringstiden är antalet månader som efterfrågas. Att minska antalet månader från tre till ett minskar genereringstiden avsevärt, men att minska tidsintervallet från en månad till en vecka har inte någon stor inverkan på rapportgenereringstiden.
* **Antal mätvärden**: När antalet mätvärden ökar ökar, ökar rapportens körtid. När du tar bort mätvärden tar det ofta längre tid att generera rapporter.
* **Antal uppdelningar**: I en rapport representerar varje uppdelning en separat begäran. Även om enskilda förfrågningar kan slutföras snabbt, kan tusentals uppdelningar i en enda rapport göra rapportgenereringstiden avsevärt långsammare och påverka rapportsvitens kö.
* **Segmentkomplexitet**: Segment som beaktar många dimensioner eller har många (24+) regler ökar bearbetningens påverkan och ökar tiden för rapportgenerering.
* **Antal unika värden**: Rapporter som innehåller hundratusentals unika värden genererar långsammare än rapporter som innehåller färre unika värden, även om segmentet eller filtret minskar antalet värden som slutligen visas i en rapport. En rapport som till exempel visar söktermer genererar vanligtvis långsammare än andra rapporter, även om ett filter används för att bara visa söktermer som innehåller ett visst värde.

## Andra rapporteringsalternativ

Följande riktlinjer hjälper till att öka tillförlitligheten vid leverans av rapporter:

* Använd Data warehouse för att begära rapporter som innehåller många uppdelningar eller mätvärden. data warehouse är utformat för att generera dessa typer av rapporter.
* Schemalägg rapporter som ska köras under icke-toppvärdestimmar. Detta ökar sannolikheten för att en rapport returneras eftersom begärandekön för en rapportsvit troligtvis är tom under den tiden.
* Report Builder kan användas för att dela upp rapporter i mindre tidsintervall och begäranden som innehåller färre mått. Du kan sedan använda den inbyggda Excel-funktionen för att sammanfoga data från olika förfrågningar i en enda rapport.
