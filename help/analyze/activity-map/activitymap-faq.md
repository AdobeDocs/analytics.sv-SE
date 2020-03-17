---
description: Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i aktivitetskartan.
title: Vanliga frågor om aktivitetskartan
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Vanliga frågor om aktivitetskartan

Vanliga frågor och svar om hur du konfigurerar, konfigurerar och använder funktioner i aktivitetskartan.

## Implementering och AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**F: Vilka är implementeringsstegen för att aktivera den nya aktivitetskartan?**

S: Granska [Aktivera aktivitetskarta](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**F: Har alla Analytics-kunder tillgång till sidan ActivityMap Enablement för Admin Tools?**

S: Adobe SiteCatalyst-kunder har inte tillgång till sidan Aktivitetskarta på Admin Console. Endast företag som omfattas av Adobe Analytics Standard och Adobe Analytics Premium har tillgång till den här konfigurationssidan.

**F: Kan den nya AppMeasurement-koden konfigureras via Dynamic Tag Management (DTM)?**

S: Ja, du kan [manuellt implementera](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) den nya AppMeasurement-koden.

**F: Vilka är de stora förändringarna i AppMeasurement v1.6-biblioteket?**

S: Den enda förändringen i AppMeasurement v1.6 finns i metoden för spårning av aktivitetskarta som kräver en samling av sidnamn, länk-ID och region-ID.

**F: Kommer AppMeasurement att introduceras på domännivå i stället för på specifika sidor?**

S: AppMeasurement introduceras på rapportsvitsnivå. Rapportsvitens nivå är vanligtvis associerad med en domännivå, men detta skiljer sig åt för varje implementering.

**F: DTM läser automatiskt in en äldre version (1.3.4) av Visitor-API:t än vad Activity Map vill (1.5.1). Är detta ett problem?**

S: Nej. Funktionen för aktivitetskarta är inte beroende av VisitorAPI.

## Program för aktivitetskarta {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**F: Kan jag använda Activity Map om jag inte tidigare har använt ClickMap för besökare på min webbplats?**

S: Att ha den äldre versionen - som nu helt enkelt kallas ClickMap - installerad är inte en förutsättning för att den nya versionen ska kunna implementeras. Adobe fortsätter att ge support för den äldre versionen under en begränsad tidsperiod.

**F: Vilka webbläsare och versioner stöds av Activity Map?**

S: Vi stöder endast den senaste versionen av de fyra huvudwebbläsarna (Chrome, Firefox, Safari och IE).

**F: Vilka är standardinställningarna för övertäckning?**

S: Som standard visas ALLA länkar som har samlade data på aktivitetskartan.

När popup-paneler visas ovanpå kundens webbsidor kan övertäckningar som tillhör länkar som finns under popup-panelen visas ovanpå popup-panelen.

**F: Varför saknas vissa rankade objektövertäckningar?**

S: Vissa rankade länkar kan vara dolda på sidan (t.ex. undermenylänkar). Därför visas inte motsvarande länkövertäckningar. Därför kan du förvänta dig att övertäckningsgraderingar som saknar vissa specifika rangordningsvärden, eftersom rangordningen beräknas för alla länkar på sidan (den nuvarande + de dolda).

**F: Hur bestäms länkrankningen i rapporten Alla länkar?**

* I **läget Övertoning** och **Bubbel** : Rankningen bestäms av måttkolumnen. För länkar med samma måttvärde baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.
* I läget **Gainer &amp; Loser** bestäms rangordningen huvudsakligen av kolumnen % vinst. För länkar med samma ökning baseras rangordningen ytterligare på länk-ID:ts alfabetiska ordning.

**F: Varför samlas inte data för länkklickning in när aktivitetskartan körs?**

S: Aktivitetskartan används, men data för länkklickning samlas inte in av Analytics-taggen. Detta beteende följer beteendet för plugin-programmet ClickMap.

**F: Varför visas samma mått flera gånger i den nedrullningsbara menyn för mätvärden?**

S: Activity Map listar mått för alla rapportsviter. Det innebär att du kan förvänta dig duplicering om företaget inte har genomgått en [metrisk konsolideringsprocess](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

Med listrutan Metrisk kan du begränsa listan med beräknade värden till de som är tilldelade till den besökta sidans rapportserie.

**F: Hur skiljer sig rapporten Activity Map All Links från rapporten Reports &amp; Analytics Activity Map?**

S: För att hämta rapporten Alla länkar i aktivitetskartan skapar vi en delningsbegäran enligt följande: Sida för aktivitetskarta = &quot;besökd sida&quot;, uppdelad efter länk&amp;region för aktivitetskarta i `<list of link&regions present in the page at rendering time>`.

Om du vill få en motsvarande rapport i Rapporter och analyser måste du först navigera till rapporten Activity Map Page. Där kan du filtrera efter det besökta sidnamnet i aktivitetskartan. Det besökta sidnamnet visas i den vänstra kolumnen på panelen Information om aktivitetskartan. När sidan har hittats kan du dela upp från den sidan och välja Aktivitetskarta, länkar och regioner som en sekundär dimension.

Det är dock viktigt att komma ihåg att den erhållna rapporten i FoA innehåller alla länkar och regioner som samlats in för den sidan. Men Activity Map rapporterar bara länkar och regioner som för närvarande finns på webbsidan. Om du har en nyhetswebbplats visar den bara data för den nyhetsartikel som finns just nu, och inte för de nyhetsartiklar som fanns tidigare under dagen.

**F: Hur fungerar Activity Map med sidor som innehåller flera taggar som listar flera rapportsviter?**

S: Som standard används rapportsviten som är kopplad till den första taggen som skickas av sidan.

Du kan välja en annan taggad rapportserie via fliken Inställningar för aktivitetskarta > Övriga.

**F: Hur länge söker Activity Map efter analystaggen?**

S: Vi söker efter Analytics-taggen i upp till 20 sekunder efter en händelse om att sidan har slutförts.

**F: Hur hanterar Activity Map dynamiskt innehåll?**

S: Aktivitetskartan kontrollerar varannan sekund om det finns några förändringar i webbsidans tillstånd, till exempel:

* HTML-innehåll som har blivit synligt
* dolt HTML-innehåll
* Nytt HTML-innehåll som injicerats

Om innehållet är dolt eller visas, ändrar programmet automatiskt läget för berörda länkar (och därmed övertäckningar) från dolt till visat eller från visat till dolt.

Om nytt innehåll injiceras hämtar programmet de associerade länkarna, hämtar analysdata för dem och lägger till övertäckningar för dessa länkar.

**F: Vilka mått baseras sidflödesrapporten på?**

S: Alla data som visas baseras på sidvisningar.

**F: Kan du förklara hur aktivitetskartan fungerar med olika typer av sidor?**

*Webbsida utan Analytics-tagg*

Ett varningsmeddelande visas under verktygsfältet som anger att det inte finns någon tagg.

*Webbsida med inkompatibel Analytics-tagg (AppMeasurement v1.5 eller tidigare)*

Ett varningsmeddelande visas som anger att du behöver (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) uppgradera sidkoden till v1.6.

*Webbsida med kompatibel Analytics-tagg (AppMeasurement v1.6 eller senare), men rapportering av aktivitetskarta har inte aktiverats i Admin Tools*

Ett varningsmeddelande visas som anger att du måste be administratören att \[Aktivera rapporten för aktivitetskartan\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;).

**F: Kan jag exportera aktivitetskarta (contextData) via[Analytics Data Feed](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)?**

S: Nej.

## Segmentering i aktivitetskarta {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**F: Är segment kopplade till enskilda användarsegment? Eller finns delade administratörsnivåsegment tillgängliga i aktivitetskartan?**

S: Aktivitetskartan ärver era segment på administratörsnivå (rapporteringssegment) från Analytics.

**F: Fungerar segment i Live-läge?**

S: Nej, segment fungerar inte i Live-läge. Funktionen motsvarar den i realtidsrapporter i rapporter och analyser.

## Virtuella rapportsviter {#section_BDB0CA9E732F478EAC349A79753A78DB}

**F: Är aktivitetskartan kompatibel med virtuella rapportsviter?**

S: Ja. På grund av begränsningar i den virtuella rapportsviten är dock inte Live-läget för aktivitetskartan kompatibelt med virtuella rapportsviter.
