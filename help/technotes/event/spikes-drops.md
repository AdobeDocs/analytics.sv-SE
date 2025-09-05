---
title: Felsöka tagningar och datasläppningar
description: Läs om möjliga orsaker till varför du kan se dramatiska ökningar eller minskningar i trendrapporter.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
feature: Curate and Share, Data Configuration and Collection
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 0%

---

# Felsöka tagningar och datasläppningar

När din webbplats samlar in data finns det många externa faktorer som kan påverka datainsamling eller rapportering drastiskt. Nedan följer en lista med möjliga förklaringar till varför vissa variabler eller den totala trafiken ökar eller minskar avsevärt.

När du fastställer orsaken och går mot en lösning, kan du mäta hur händelsen påverkar dina data och avgöra hur du vill fortsätta. Mer information finns på [översiktssidan](overview.md).

## Trafikdroppar

Trafikdroppar indelas i två avsnitt: partiella data och nolldata.

### Potentiella orsaker till att data saknas helt (nollvärden rapporteras)

* **RapporteringsSuite-svarstid**: Ibland kan en rapportserie få [fördröjning](../latency.md) på grund av ett antal faktorer. Många latensproblem löses inom några timmar. Om du är intresserad av en viss rapportsserie kan du kontakta Adobe kundtjänst och ange den berörda rapportsvitens-ID:t.
* **Implementeringsborttagning**: Ibland när en organisation gör implementeringsändringar eller omstrukturerar sin webbplats förbises implementeringen av Analytics. Samarbeta med utvecklare i organisationen för att implementera koden på din webbplats igen.
* **Problem med gränssnitt/cachelagring för analyser**: I sällsynta fall innehåller webbläsarens cache ogiltiga data som gör att alla rapporter returnerar nollor. Lös problemet genom att rensa webbläsarens cookies och cache. Om det inte fungerar att rensa dina cookies/cacheminnen kan du kontakta Kundtjänst med den rapport och det datumintervall som saknas. De kan duplicera problemet och tillhandahålla ytterligare information.
* **Analystillgänglighet**: Kontrollera [status.adobe.com](https://status.adobe.com/products/1173/) för eventuella problem med datainsamling eller databearbetning.

### Potentiella orsaker till att data saknas delvis eller till minskad trafik

* **Implementeringsändringar**: Använd [debugger](/help/implement/validate/debugger.md) för att verifiera att de önskade dimensionerna fungerar.
* **Minskad hänvisningstrafik**: Om en populär banderoll eller hyperlänk på en annan plats tas bort kan det orsaka en dramatisk minskning av trafiken. Trend dimensionen [Refererande domäner](/help/components/dimensions/referring-domain.md) från före och efter släppningen för att ytterligare undersöka.
* **Platsprestandaproblem**: Felaktig distribution av trafik via belastningsutjämnare eller serverproblem som är värd för din webbplats kan bidra till en minskning av analysrapporteringen. Arbeta med teamet inom organisationen som hanterar webbplatsens integritet och hälsa för att undersöka eventuella prestandaproblem.
* **Förändringar i den naturliga sökrankningen**: Trafiken kan minska om en annan webbplats har din naturliga sökrankning för några av dina nyckelord. Den här minskningen är särskilt tydlig om webbplatsen inte längre är på den första sidan i sökresultatet. Trend dimensionen för [sökmotorer](/help/components/dimensions/search-engine.md) för ytterligare forskning.
* **Ändringar i PPC-annonsering**: Om du ändrar annonsrubriker och beskrivningar för befintliga kampanjer kan det påverka din kvalitetspoäng. I allmänhet innebär en hög kvalitet att nyckelordet utlöser annonser i en högre position och till en lägre kostnad per klick. Trend dimensionen [Sök nyckelord - betald](/help/components/dimensions/search-keyword.md) för att få mer information.

## Trafiktoppar

Trafiktoppar indelas i två delar: nästan dubbla data och andra orsaker.

### Möjliga orsaker till att ha nästan eller exakt dubbelt så stora data som förväntat

* **Flera bildbegäranden i en implementering**: Om implementeringen innehåller mer än ett [`t()`](/help/implement/vars/functions/t-method.md) metodanrop per sida dubbleras alla insamlade data. Använd felsökaren på din webbplats och se efter om det finns flera bildbegäranden som kan fånga upp dubbletter.
* **Duplicerade datakällfiler överförda**: Om din organisation använder [datakällor](/help/import/data-sources/overview.md) kan en användare i din organisation överföra samma fil två gånger till Adobe Analytics. Att utföra den här duplicerade överföringen fördubblar effektivt data i rapporteringen, vilket ger upphov till trafiksprång.

### Andra potentiella orsaker till ökad trafik

* **Spindlar eller spindlar**: Om du ser en stor plötslig ökning av trafiken är det första du behöver leta efter möjligheten att ha en spindel eller robot. Det kan ibland vara svårt att identifiera objekt eftersom de har olika sätt att köra kod på webbplatsen. Skapa en Data Warehouse-rapport med IP som dimension för att se vilka adresser som orsakar störst trafik. Du kan sedan använda antingen [Punktregler](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) eller en VISTA-regel för att ta bort både trafik och eventuell framtida rapportering.
* **Lanserade kampanjer**: Marknadsföringsaktiviteter som e-postkampanjer eller optimering av sökmotorer kan potentiellt orsaka en trafiktopp på din webbplats. Trend dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md) om du vill söka ytterligare. Det kan också hjälpa er att kontakta marknadsföringsteamet för att säkerställa att toppen var avsiktlig.
* **Miljörelaterade eller indiciella orsaker**: Om en semester eller en omständighet inträffar (en viktig händelse där din plats är en känd resurs, eller om andra organisationers övriga marknadsföringssatsningar förekommer) kan trafiken öka på din plats. Det är svårt att felsöka den exakta orsaken, eftersom det finns ett nästan obegränsat antal orsaker till varför trafiken kan öka. Detta är dock några av de viktigaste skälen att avgöra så att ni kan dra nytta av dem och fatta lämpliga affärsbeslut. Att trenda dimensionen [Sida](/help/components/dimensions/page.md) eller [Referer](/help/components/dimensions/referrer.md) är troligen den bästa platsen att börja på när du ska fastställa trafikens källa.

Om ingen av ovanstående orsaker ligger bakom ökad eller minskad trafik på er webbplats, kontakta Adobe kundtjänst. De kan hjälpa till att hitta källan till trafiktoppen eller -släppningen. När du skapar incidenten ska du instruera agenten om hur den ska återskapa en specifik rapport som tydligt illustrerar toppen eller släppningen.
