---
title: Enhetsövergripande analys
description: Ändra era data från enhetsfokuserade till personfokuserade genom att sammanfoga enhetsdata.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---


# Enhetsövergripande analys

Analytics för flera enheter är en funktion som omvandlar Analytics från en enhetscentrerad vy till en personcentrerad vy. Därför kan analytiker förstå användarbeteende som fungerar på olika webbläsare, enheter och appar. Adobe stöder två övergripande arbetsflöden för att länka samman enhetsdata:

* [**Fältbaserad stygn **](field-based-stitching.md): Gör att du kan välja en Analytics-variabel som bas för sammanfogning mellan enheter i en virtuell rapportserie. Använder deterministisk matchning för att länka samman enheter. Adobe rekommenderar att du använder fältbaserad sammanfogning för de flesta deterministiska matchningsfall.
* [**Enhetsdiagram **](device-graph.md): CDA kommunicerar med ett enhetsdiagram för att knyta ihop enheter. I co-op-diagrammet används både deterministisk och sannolik matchning.

Med CDA kan du besvara frågor som:

* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När enheter sammanfogas överförs variabel beständighet mellan olika enheter. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren hittar din mobilapp, installerar den och gör så småningom ett köp på sin mobila enhet. Med Cross-Device Analytics kan intäkterna tillskrivas annonsen de klickade på på sin dator.

Av en anda av partnerskap och transparens vill vi att våra kunder ska vara medvetna om vår användning av Microsoft Azure tillsammans med Analytics för olika enheter. Adobe använder Azure för att lagra enhetsdiagramdata och för att utföra sammanfogning mellan enheter. Därför skickas data från Adobe Analytics fram och tillbaka mellan Adobes datacenter och Adobes tilldelade instanser av Microsoft Azure.

Se [Journey IQ: Analytics Spark-sidan](http://adobe.ly/aacda) för flera enheter om du vill veta mer om funktionerna i Analytics för olika enheter.

## Förutsättningar

Användning av CDA kräver allt av följande: [Fältbaserade sammanfogningsmetoder](field-based-stitching.md) och [enhetsdiagrammetoder](device-graph.md) har också sina egna specifika förutsättningar.

* Ett kontrakt måste undertecknas med Adobe som innehåller Adobe Analytics Ultimate.
* Enhetsövergripande Analytics aktiveras per rapport. Adobe rekommenderar en rapportserie som innehåller data för olika enheter, vilket innebär data från flera olika typer av enheter (webb, app, osv.). Vissa organisationer hänvisar till detta koncept som en&quot;global&quot; rapportserie, även om CDA inte strikt måste vara global ur ett geografiskt perspektiv.

## Begränsningar

Analytics för flera enheter är en banbrytande och robust funktion, men har begränsningar i hur den kan användas. [Fältbaserade stygn](field-based-stitching.md) - och [enhetsgraf](device-graph.md) -metoder har också egna specifika begränsningar.

* CDA är endast tillgängligt via Analysis Workspace.
* Enhetsövergripande Analytics fungerar inte i alla rapportsviter, och inte heller kombineras data från flera rapportsviter.
* Adobe Analytics rapporteringsprogram kan inte mappa till mer än en IMS-organisation. Eftersom CDA sammanfogar enheter inom en viss rapportserie kan CDA inte användas för att sammanfoga data över flera IMS-organ.
* CDA är för närvarande inte kompatibelt med kundattribut. Dessa två funktioner kan sammanfalla i separata virtuella rapportsviter som refererar till samma källrapportsserie.
* Analytics för flera enheter använder ett virtuellt rapportpaket och rapporterar tidsbearbetning, som har egna begränsningar. Mer information om dessa begränsningar finns i [Virtuella rapportsviter](../vrs/vrs-about.md) och [Rapporttidsbearbetning](../vrs/vrs-report-time-processing.md) .
* 1.4-API:t stöds inte. Power BI-anslutningar och Report Builder är båda beroende av 1.4-API:t och är därför inte kompatibla med CDA.
* Historiska data i den virtuella rapportsviten ändras baserat på hur Adobe identifierar och sammanfogar enheter. Data i källrapportsviten ändras inte.
