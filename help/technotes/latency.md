---
description: Följande information kan hjälpa till att felsöka problem med rapportsvitens latens i Analytics-data.
keywords: data saknas;långsam
title: Datatillgänglighet och fördröjning
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Datatillgänglighet och fördröjning i Adobe Analytics

Du kan vanligtvis förvänta dig att få se fullständiga data i rapporter 2 timmar efter att data har samlats in. Följande information kan hjälpa till att felsöka problem med rapportsvitens latens i Analytics-data.

## Förstå databatchning

Varje datainsamlingsserver hämtar in och bearbetar råanalysdata och överför sedan batchdata timvis för rapportering. Överföringsprocessen tar vanligtvis 30 minuter, så normal fördröjning för trafik som sker direkt efter den föregående överföringsprocessen är ungefär 90 minuter (60 minuter tills nästa batchöverföring sker, sedan 30 minuter för filöverföring och visning). För trafik som sker direkt före en överföring kan datalatensen vara så kort som 30 minuter (0 minuter tills nästa batchöverföring sker, sedan 30 minuter för filöverföring och visning).

Vid behov kan Adobe kundtjänst aktivera 30 minuters batchvis dataöverföring (i stället för timvis) för dina mest använda rapportsviter.

## Medarbetare till fördröjning

Latens är en fördröjning som är längre än de vanliga två timmarna det tar för datainsamlingsservrar att bearbeta data helt. Den påverkar inte datainsamlingen. data samlas fortfarande in för en fungerande implementering, oavsett hur länge en rapportsvit är tillgänglig. Dess allvarlighetsgrad (hur aktuella data är) och längd (hur lång tid det tar att lösa) kan variera mycket. Den är vanligtvis begränsad till en enda rapportserie.

Latens orsakas av en av följande allmänna kategorier:

* **Oväntad trafiktoppning:** Den här typen av fördröjning inträffar när fler data skickas till en rapportsvit än vad som har bekräftats eller förväntades enligt avtal. Det är den vanligaste orsaken till latens.
* **Vanliga maskinvaruproblem:** Adobe har förstklassiga strategier för hantering och övervakning av datacenter, dataredundans och maskinvarans tillförlitlighet. Maskinvaran uppdateras regelbundet och i samband med publicerade underhållsfönster. Nödunderhåll av felaktig maskinvara kan kräva ett nödvändigt och tillfälligt avbrott i databearbetningen (inte i datainsamlingen) eftersom ersättningsmaskinvara ansluts. Detta tillfälliga stopp i bearbetningen kan leda till märkbar fördröjning.
* **Onormala data:** Onaturliga datamönster, till exempel ovanligt långa besök som orsakas av en robot eller crawler, kan tillfälligt öka vissa bearbetningsbelastningar som resulterar i fördröjning.

## Funktioner som är beroende av latens

Vissa funktioner i Adobe Experience Cloud har en kort latenstid utöver den vanliga bearbetningstiden.

* Analyser för Target (A4T) kräver ytterligare 5-10 minuters fördröjning så att insamlade data från båda plattformarna kan lagras i samma träff.
* Tidsstämplade data kräver ytterligare tid på grund av olika servrar som dessa data bearbetas på. Tidsstämplade träffar som tas emot i eller nära realtid kan ta upp till 15 minuter. Träffar som tas emot med en tidsstämpel från igår kan ta upp till två timmar. Äldre träffar kan ta längre tid, vilket kan öka varje dag upp till ett tak på cirka 24 timmar.

## Sätt att minska eller förhindra fördröjning

Det finns flera strategier för att förhindra fördröjning eller minska återställningstiden när den inträffar:

* **Meddela Adobe om förväntade trafiktoppar:** Även om det är omöjligt att förutse varje trafiksprång på er webbplats, kan det finnas fall där ni förväntar er en betydande ökning av trafiken. Exempel är en särskilt framgångsrik semesterperiod, eller kort efter en stor kampanjkampanj. I dessa fall kan Adobe ge er organisation möjlighet att informera oss om förväntade trafikökningar så att vi kan tilldela ytterligare bearbetningsresurser till ert rapporteringsprogram. Se [Schemalägg en trafiktoppning](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) i användarhandboken för Admin om du vill veta hur du kan meddela Adobe om ökad trafik.
* **Överväg att läsa in när du aktiverar nya funktioner:** Vissa funktioner är mer bearbetningsintensiva än andra. Ju fler funktioner som är aktiverade i en rapportserie, desto svårare är det att återställa efter fördröjning. När du aktiverar funktioner i en rapportserie bör du tänka på följande funktioner som ökar mängden data som ska bearbetas:

   * Implementera mer än 20 händelser på samma sida
   * Komplexa VISTA-regler
   * Mer än 20 värden i variabeln products
   * Händelseserialisering

* Aktivera IAB-punktsfiltrering: [Punktfiltrering](/help/admin/admin/bot-removal/bot-removal.md) kan minska fördröjningen avsevärt om rapportsviten ofta används av botar eller crawler. Vi rekommenderar att du använder IAB-robotlistan eftersom den uppdateras och underhålls av [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). En användare kan anpassa sina egna robotregler för att komplettera dem från IAB.

## Vad du ska göra med svarstid

I de fall där fördröjning inträffar kan du vara säker på att Adobe proaktivt övervakar bearbetningsflödet och gör allt som är möjligt för att återställa bearbetningstiden till normal så snabbt som möjligt. Många latensproblem löses inom några timmar. Om du är orolig för en viss rapportserie kan en av de användare i organisationen som stöds kontakta Kundtjänst med det rapportsvit-ID som har fördröjning. Adobe kan validera latensen och informera dig när problemet förbättras och är löst.
