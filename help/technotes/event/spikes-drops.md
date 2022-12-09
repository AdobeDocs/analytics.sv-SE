---
title: Felsöka tagningar och datasläppningar
description: Läs om möjliga orsaker till varför du kan se dramatiska ökningar eller minskningar i trendrapporter.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 0%

---

# Felsöka tagningar och datasläppningar

När din webbplats samlar in data finns det många externa faktorer som kan påverka datainsamling eller rapportering drastiskt. Nedan följer en lista med möjliga förklaringar till varför vissa variabler eller den totala trafiken ökar eller minskar avsevärt.

När du fastställer orsaken och går mot en lösning, kan du mäta hur händelsen påverkar dina data och avgöra hur du vill fortsätta. Se [översiktssida](overview.md) för mer information.

## Trafikdroppar

Trafikdroppar indelas i två delar: partiella data och nolldata.

### Möjliga orsaker till att data saknas helt (nollvärden rapporteras)

* **Rapportsvitsvarstid**: Ibland kan en rapportserie upplevas [latens](../latency.md) på grund av ett antal faktorer. Många latensproblem löses inom några timmar. Om du är intresserad av en viss rapportsserie kontaktar du Adobe kundtjänst med den berörda rapportsvitens-ID:t.
* **Borttagning av implementering**: Ibland när en organisation gör implementeringsändringar eller omstrukturerar sin webbplats förbises implementeringen av Analytics. Samarbeta med utvecklare i organisationen för att implementera koden på din webbplats igen.
* **Problem med gränssnitt/cachning för analyser**: I enstaka fall innehåller webbläsarens cache ogiltiga data som gör att alla rapporter returnerar nollor. Lös problemet genom att rensa webbläsarens cookies och cache. Om det inte fungerar att rensa dina cookies/cacheminnen kan du kontakta kundtjänst och uppge den rapport och det datumintervall som saknas. de kan duplicera problemet och lämna ytterligare information.
* **Analystillgänglighet**: Kontrollera [status.adobe.com](https://status.adobe.com/products/1173/) för eventuella problem med datainsamling eller databehandling.

### Potentiella orsaker till att data saknas delvis eller till minskad trafik

* **Implementeringsändringar**: Använd [debugger](/help/implement/validate/debugger.md) för att validera att de önskade dimensionerna fungerar.
* **Minskad hänvisande trafik**: Om en populär banners eller hyperlänk på en annan webbplats tas bort kan det orsaka en dramatisk trafikminskning. Trend the [Refererande domäner](/help/components/dimensions/referring-domain.md) en dimension från före och efter det att forskningsverksamheten har släppts vidare.
* **Platsprestandaproblem**: Felaktig distribution av trafik via belastningsutjämnare eller serverproblem som är värd för din webbplats kan bidra till en minskning av analysrapporteringen. Arbeta med teamet inom organisationen som hanterar webbplatsens integritet och hälsa för att undersöka eventuella prestandaproblem.
* **Förändringar i den naturliga rangordningen av sökningar**: Trafiken kan minska om en annan webbplats ligger i din naturliga sökrankning för några av dina nyckelord. Den här minskningen är särskilt tydlig om webbplatsen inte längre är på den första sidan i sökresultatet. Trend the [Sökmotorer](/help/components/dimensions/search-engine.md) En dimension till forskning.
* **Ändringar i PPC-reklam**: Om ni ändrar annonsrubriker och beskrivningar för befintliga kampanjer kan detta påverka er kvalitetspoäng. I allmänhet innebär en hög kvalitet att nyckelordet utlöser annonser i en högre position och till en lägre kostnad per klick. Trend the [Söknyckelord - betalt](/help/components/dimensions/search-keyword.md) En dimension till forskning.

## Trafiktoppar

Trafiktoppar indelas i två delar: nästan dubbla data och andra orsaker.

### Möjliga orsaker till att ha nästan eller exakt dubbelt så stora data som förväntat

* **Flera bildbegäranden inom en implementering**: Om implementeringen innehåller fler än ett [`t()`](/help/implement/vars/functions/t-method.md) anrop per sida, vilket innebär att alla insamlade data dubbleras. Använd felsökaren på din webbplats och se efter om det finns flera bildbegäranden som kan fånga upp dubbletter.
* **Duplicerade datakällfiler har överförts**: Om din organisation använder [Datakällor](/help/import/c-data-sources/datasrc-home.md), kan en användare i din organisation överföra samma fil två gånger till Adobe Analytics. Att utföra den här duplicerade överföringen fördubblar effektivt data i rapporteringen, vilket ger upphov till trafiksprång.

### Andra potentiella orsaker till ökad trafik

* **Spindlar och spindlar**: Om man ser en stor plötslig ökning av trafiken är det första man ska leta efter möjligheten till en spindel eller robot. Det kan ibland vara svårt att identifiera objekt eftersom de har olika sätt att köra kod på webbplatsen. Skapa en Data warehouse-rapport med IP som dimension för att se vilka adresser som orsakar störst trafik. Du kan sedan använda antingen [Punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) eller en VISTA-regel som eliminerar båda trafiken från framtida rapportering.
* **Lanserade kampanjer**: Marknadsföringssatsningar som e-postkampanjer eller optimering av sökmotorer kan potentiellt orsaka en trafiktopp på er webbplats. Trend the [Spårningskod](/help/components/dimensions/tracking-code.md) En dimension till forskning. Det kan också hjälpa er att kontakta marknadsföringsteamet för att säkerställa att toppen var avsiktlig.
* **Miljörelaterade eller indiciella orsaker**: Om en semester- eller individhändelse inträffar (en viktig händelse där din webbplats är en känd resurs eller andra organisationers återstående marknadsföringssatsningar) kan trafiken öka på din webbplats. Det är svårt att felsöka den exakta orsaken eftersom det finns ett nästan obegränsat antal orsaker till varför trafiken kan öka. Detta är dock några av de viktigaste skälen att avgöra så att ni kan dra nytta av dem och fatta lämpliga affärsbeslut. Tränar [Sida](/help/components/dimensions/page.md) eller [Referent](/help/components/dimensions/referrer.md) är troligen den bästa utgångspunkten när det gäller att fastställa trafikens källa.

Om ingen av ovanstående orsaker ligger bakom ökad eller minskad trafik på er plats, kontakta Adobe kundtjänst. De kan hjälpa till att hitta källan till trafiktoppen eller -släppningen. När du skapar incidenten ska du instruera agenten om hur den ska återskapa en specifik rapport som tydligt illustrerar toppen eller släppningen.
