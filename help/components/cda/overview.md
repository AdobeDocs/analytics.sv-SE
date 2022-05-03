---
title: Enhetsövergripande analys
description: Ändra era data från enhetsfokuserade till personfokuserade genom att sammanfoga enhetsdata.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Enhetsövergripande analys

Enhetsövergripande analys är en funktion som omvandlar analyser från enhetscentrerad vy till personcentrerad vy. Därför kan analytiker förstå användarbeteende som fungerar på olika webbläsare, enheter och appar. Adobe stöder två övergripande arbetsflöden för att länka samman enhetsdata:

* [**Fältbaserad stygn**](field-based-stitching.md): Rekommenderas för sammanfogning eftersom endast deterministisk matchning används för att länka samman enheter.
Gör att du kan välja en Analytics-variabel som bas för sammanfogning mellan enheter i en virtuell rapportserie.
* [**Enhetsdiagram**](device-graph.md): CDA kommunicerar med ett enhetsdiagram för att knyta ihop enheter. I co-op-diagrammet används både deterministisk och sannolik matchning.

>[!NOTE]
>
>Läs mer om [Device Co-op - slut på livscykeln](https://experienceleague.adobe.com/docs/device-co-op/using/about/device-co-op-eol.html).

Med CDA kan du besvara frågor som:

* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När enheter sammanfogas överförs variabel beständighet mellan olika enheter. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren hittar din mobilapp, installerar den och gör så småningom ett köp på sin mobila enhet. Med Enhetsövergripande analys kan ni attribuera intäkterna på den mobila enheten till annonsen som de klickade på på sin dator.

Av en anda av partnerskap och transparens vill vi att våra kunder ska vara medvetna om vår användning av Microsoft Azure tillsammans med Cross-Device Analytics. Adobe använder Azure för att lagra enhetsdiagramdata och för att utföra sammanfogning mellan enheter. Därför skickas Adobe Analytics-data fram och tillbaka mellan Adobe databehandlingscenter och Adobe&#39;s provisionerade instanser av Microsoft Azure.

Se [Resa-IQ: Spark-sida för analys av flera enheter](https://adobe.ly/aacda) om du vill veta mer om funktionerna i Enhetsövergripande analys.

## Förutsättningar

Användning av CDA kräver allt av följande: [Fältbaserad stygn](field-based-stitching.md) och [Enhetsdiagram](device-graph.md) -metoder har också sina egna specifika förutsättningar.

* Ett kontrakt måste undertecknas med Adobe som innehåller Adobe Analytics Ultimate.
* Enhetsövergripande analys aktiveras per rapport. Adobe rekommenderar att du skapar en rapportserie som innehåller data för olika enheter, vilket innebär data från flera olika typer av enheter (webb, app, osv.). Vissa organisationer hänvisar till detta koncept som en&quot;global&quot; rapportserie, även om CDA inte strikt måste vara global ur ett geografiskt perspektiv.

## Begränsningar

Enhetsövergripande analys är en banbrytande och robust funktion, men har begränsningar i hur den kan användas. [Fältbaserad stygn](field-based-stitching.md) och [Enhetsdiagram](device-graph.md) -metoder har också egna specifika begränsningar.

* CDA är endast tillgängligt via Analysis Workspace.
* Enhetsövergripande analyser fungerar inte i alla rapportsviter och inte heller kombineras data från flera rapportsviter.
* Adobe Analytics rapporteringsprogram kan inte mappa till mer än ett organisations-ID. Eftersom CDA sammanfogar enheter inom en viss rapportserie kan CDA inte användas för att sammanfoga data över flera organisations-ID:n.
* CDA använder en komplex bearbetningsprocess, med flera beroende komponenter. Detta körs parallellt med rapportarbetsflödet i den grundläggande analysen. Därför förväntas en datamatchningsavvikelse på ungefär 1 % för det totala antalet träffar mellan den ursprungliga rapportsviten och den virtuella CDA-rapportsviten.
* Enhetsövergripande analys använder ett virtuellt rapportpaket och rapporttidsbearbetning, som har egna begränsningar. De stöder till exempel för närvarande inte variabler för marknadsföringskanaler. Se [Virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en) och [Bearbetning av rapporttid](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en#report-time-processing-limitations) för mer information om dessa begränsningar.
* Privat diagram använder samma ID-synk som de som används av [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#customer-attributes) i Experience Cloud och Adobe Analytics. Men de virtuella CDA-rapporteringssviterna (oavsett om de baseras på ett privat diagram eller fältbaserad sammanfogning) är inte kompatibla med resten av funktionen för kundattribut. Med andra ord är kundattributbaserade dimensioner inte tillgängliga för användning med virtuella CDA-rapportsviter.
* CDA är för närvarande inte kompatibelt med A4T.
* 1.4-API:t stöds inte. Power BI-anslutningar och Report Builder är båda beroende av 1.4-API:t och är därför inte kompatibla med CDA.
* Den aktiva övervakningen av CDA-sammanslagningsprocessen av Adobe är begränsad till enbart produktionsrapportsviter.
* CDA är för närvarande inte kompatibelt med Adobe Analytics [API för datareparation](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md)
* Historiska data i den virtuella rapportsviten ändras baserat på hur Adobe identifierar och syr ihop enheter. Data i källrapportsviten ändras inte.
* Stitchade data har en fördröjning på 8 till 12 timmar.
* Mappningshistorikdata för en viss enhet lagras i upp till ett år.
* Om en enhet når ett mycket stort antal mappningshistorikposter inom ett år trunkeras mappningshistoriken. Den exakta gränsen beror på vilket sömnalternativ som används.
