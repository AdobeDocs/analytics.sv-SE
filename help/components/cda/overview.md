---
title: Enhetsövergripande analys
description: Lär dig hur du ändrar data från enhetsfokuserade till personfokuserade genom att sammanfoga enhetsdata.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: 7d4471be41522d385406574e4f00c31e0704ce27
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---

# Enhetsövergripande analys

{{available-existing-customers}}

>[!WARNING]
>
>Enhetsdiagram inom enhetsövergripande analys är inte längre tillgängligt den **31 december 2025**. Växla en eventuell aktiverad virtuell rapportsvit för enhetsdiagram till den [fältbaserade metoden](/help/components/cda/field-based-stitching.md).
>


CDA (Cross-Device Analytics) är en funktion som omvandlar analyser från en enhetscentrerad vy till en personcentrerad vy. Därför kan analytiker förstå användarbeteende som fungerar på olika webbläsare, enheter och appar. Adobe har stöd för två övergripande arbetsflöden för att länka samman enhetsdata:

* [Fältbaserad sammanfogning](field-based-stitching.md): Rekommenderat sammanfogningsalternativ eftersom endast deterministisk matchning används för att länka samman enheter.
Med fältbaserad sammanfogning kan ni välja en Analytics-variabel som bas för sammanfogning mellan enheter i en virtuell rapportserie.

* [Enhetsdiagram](device-graph.md): Enhetsövergripande analyser kommunicerar med ett privat diagram för att knyta ihop enheter.

Med CDA kan du besvara frågor som:

* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min funnel-analys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När enheter sammanfogas överförs variabel beständighet mellan olika enheter. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren hittar din mobilapp, installerar den och gör så småningom ett köp på sin mobila enhet. Med Enhetsövergripande analys kan ni attribuera intäkterna på den mobila enheten till annonsen som de klickade på på sin dator.

Microsoft Azure används för enhetsövergripande analys. Adobe använder Azure för att lagra enhetsdiagramdata och för att utföra sammanfogning mellan enheter. Därför skickas data från Adobe Analytics fram och tillbaka mellan Adobe datacenter och Adobe provisionerade instanser av Microsoft Azure.

På sidan [Cross-Device Analytics Spark](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) finns mer information om funktionerna och funktionerna i Cross-Device Analytics.

## Förutsättningar

Användning av enhetsövergripande analys kräver [fältbaserad sammanfogning](field-based-stitching.md) och [enhetsgraf](device-graph.md) metoder, och båda har sina egna specifika förutsättningar.

* Ett kontrakt måste undertecknas med Adobe som innehåller Adobe Analytics Ultimate.
* Din organisation väljer vilka rapporteringsprogram som ska aktiveras för CDA. Adobe rekommenderar rapportsviter som innehåller data mellan olika enheter, vilket innebär data från flera olika typer av enheter/webbläsare/appar. Vissa organisationer hänvisar till detta koncept som en&quot;global&quot; rapportserie, även om enhetsövergripande analyser inte strikt måste vara globala ur ett geografiskt perspektiv.

## Begränsningar

Enhetsövergripande analys är en banbrytande och robust funktion, men har begränsningar i hur den kan användas. Metoderna [Fältbaserad sammanfogning](field-based-stitching.md) och [Enhetsdiagram](device-graph.md) har också egna specifika begränsningar.

* Enhetsövergripande analys är bara tillgängligt via Analysis Workspace.
* Enhetsövergripande analyser fungerar inte i alla rapportsviter och inte heller kombineras data från flera rapportsviter.
* Adobe Analytics rapporteringsprogram kan inte mappa till mer än ett organisations-ID. Eftersom enhetsövergripande analyser sammanfogar enheter inom en given rapportserie kan enhetsövergripande analyser inte användas för att sammanfoga data över flera organisations-ID:n.
* Enhetsövergripande analys använder en komplex bearbetningsprocess, med flera beroende komponenter. Detta tillvägagångssätt körs parallellt med rapportarbetsflödet i den grundläggande analysen. Du kan förvänta dig en felmatchning av data på ungefär 1 % för det totala antalet träffar mellan den ursprungliga rapportsviten och den virtuella rapportsviten för enhetsanalys.
* Enhetsövergripande analys använder ett virtuellt rapportpaket och rapporttidsbearbetning, som har egna begränsningar. De stöder till exempel för närvarande inte variabler för marknadsföringskanaler. Mer information om de här begränsningarna finns i [Virtuella rapportsviter](/help/components/vrs/vrs-about.md) och [Rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md).
* Privat diagram använder samma ID-synk som de ID-synk som används av funktionen [Kundattribut](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) i Experience Cloud och Adobe Analytics. De virtuella rapportsviterna för enhetsanalys (oavsett om de baseras på ett privat diagram eller fältbaserad sammanfogning) är dock inte kompatibla med resten av funktionen för kundattribut. Med andra ord är kundattributbaserade dimensioner inte tillgängliga för användning med virtuella rapportsviter för analyser över flera enheter.
* Enhetsövergripande analys är för närvarande inte kompatibelt med A4T.
* 1.4-API:t stöds inte. Power BI-anslutningar och Report Builder är båda beroende av 1.4-API:t och är därför inte kompatibla med CDA.
* Den aktiva övervakningen av sammanfogningsprocessen i enhetsanalyser av Adobe är begränsad till enbart produktionsrapportsviter.
* Enhetsövergripande analys är för närvarande inte kompatibel med Adobe Analytics [API för datareparation](https://developer.adobe.com/analytics-apis/docs/2.0/)
* Historiska data i den virtuella rapportsviten ändras baserat på hur Adobe känner igen och syr ihop enheter. Data i källrapportsviten ändras inte.
* Stitchade data har en fördröjning på 8 till 12 timmar.
* Mappningshistorikdata för en viss enhet lagras i upp till ett år.
* Om en enhet når ett mycket stort antal mappningshistorikposter inom ett år, trunkeras mappningshistoriken. Den exakta gränsen beror på vilket sömnalternativ som används.
