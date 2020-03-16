---
title: Enhetsövergripande analys
description: Enhetsövergripande analys förändrar era data från att vara enhetsfokuserade till personfokuserade genom att sammanfoga enhetsdata.
translation-type: tm+mt
source-git-commit: 3e821ce7b045647c09d9548659834ffc2170163d

---


# Enhetsövergripande analys

> [!NOTE] Enhetsövergripande analysdokumentation kan komma att ändras i takt med att funktionen utvecklas ytterligare. Kontrollera regelbundet om det finns uppdateringar.

Enhetsövergripande analys är en funktion som omvandlar analyser från enhetscentrerad vy till personcentrerad vy. Den här funktionen använder Adobe Experience Platform Identity Service Co-op Graph eller Private Graph för att identifiera vilka enheter som tillhör enskilda personer och sätta ihop dem. Därför kan analytiker förstå användarbeteende som fungerar på olika webbläsare, enheter och appar. Med CDA kan du besvara frågor som:

* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När enheter sammanfogas överförs variabel beständighet mellan olika enheter. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren hittar din mobilapp, installerar den och gör så småningom ett köp på sin mobila enhet. Med Enhetsövergripande analys kan intäkterna tillskrivas annonsen de klickade på på sin dator.

Se [Journey IQ: Spark-sidan](http://adobe.ly/aacda) för analys av olika enheter om du vill veta mer om funktionerna och funktionerna i Cross-Device Analytics.

## Förutsättningar

Från och med september 2019 krävs följande för enhetsövergripande analys: Samarbeta med team inom organisationen och er kontoansvarige på Adobe för att säkerställa att ni uppfyller alla följande krav.

> [!IMPORTANT] Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när data sammanfogas.

* Organisationens data måste finnas i Adobes datacenter i Stillahavsområdet i nordväst. Stöd för datacenter i andra delar av världen planeras.
* Kontakta er kontoansvarige på organisationen för att få hjälp med följande:
   * Ett kontrakt måste undertecknas med Adobe som innehåller Adobe Analytics Ultimate.
   * Din organisation måste använda Adobe Experience Platform Identity Service Co-op Graph eller Private Graph. Se [hemsidan](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) i användarhandboken för Device Co-op.
   * Av en anda av partnerskap och transparens vill vi att våra kunder ska vara medvetna om vår användning av Microsoft Azure tillsammans med Cross-Device Analytics. Adobe använder Azure för att lagra enhetsdiagramdata och för att utföra sammanfogning mellan enheter. Därför skickas data från Adobe Analytics fram och tillbaka mellan Adobes datacenter och Adobes tilldelade instanser av Microsoft Azure.
* Enhetsövergripande analys aktiveras per rapport. Rapporteringssviter som har aktiverats för CDA kräver följande:
   * Rapportsviten får inte innehålla fler än 500 miljoner träffar per dag.
   * Adobe rekommenderar att en rapportserie innehåller data för olika enheter, vilket innebär data från flera olika typer av enheter (webb, app, osv.). Vissa organisationer hänvisar till detta koncept som en&quot;global&quot; rapportserie, även om CDA inte strikt måste vara global ur ett geografiskt perspektiv. Enhetsövergripande analyser fungerar inte i alla rapportsviter och inte heller kombineras data från flera rapportsviter.
* Implementeringen måste uppfylla följande krav:
   * Den senaste versionen av Experience Cloud ID Service måste distribueras. Se [hemsidan](https://docs.adobe.com/content/help/en/id-service/using/home.html) i användarhandboken för Experience Cloud Identity Service. De flesta implementeringar som använder Adobe Experience Platform Launch har antagligen redan ECID.
   * Anropa `setCustomerIDs` funktionen när en person kan identifieras, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Se [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) i användarhandboken för Experience Cloud Identity Service.

## Begränsningar

Enhetsövergripande analys är en banbrytande och robust funktion, men har begränsningar i hur den kan användas.

* CDA är endast tillgängligt via Analysis Workspace.
* Stitching kan inte inträffa i alla rapportsviter enligt beskrivningen i ovanstående villkor.
* Rapporteringssviter för Adobe Analytics kan inte mappa till mer än en IMS-organisation. Eftersom CDA sammanfogar enheter inom en viss rapportserie kan CDA inte användas för att sammanfoga data över flera IMS-organ.
* CDA är för närvarande inte kompatibelt med kundattribut. Kundattribut kan inte användas för att skapa en virtuell CDA-rapportsvit, inom enhetsövergripande segment eller för att rapportera inom ett Analysis Workspace-projekt som baseras på en virtuell CDA-rapportsserie.
   > [!TIP] Även om kundattribut inte kan användas i CDA är båda funktionerna beroende av `setCustomerIDs` funktionen. Dessa två funktioner kan sammanfalla i separata (virtuella) rapportsviter.
* CDA kräver antingen Co-op Graph eller Private Graph. Enhetsdiagram från tredje part stöds inte.
* Äldre analys-ID:n stöds inte. Endast besökare med Experience Cloud ID:n sys ihop.
* Kundtjänst har ännu inte fullt stöd för den här funktionen. Forum [för](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) enhetsövergripande analys kan användas för att ge support på den här funktionen, som innefattar aktiv och direkt medverkan från Adobes produktchefer.
* Enhetsövergripande analys använder ett virtuellt rapportpaket och rapporttidsbearbetning, som har egna begränsningar. Mer information om dessa begränsningar finns i [Virtuella rapportsviter](../vrs/vrs-about.md) och [Rapporttidsbearbetning](../vrs/vrs-report-time-processing.md) .
* 1.4-API:t stöds inte. Power BI-anslutningar och Report Builder är båda beroende av 1.4-API:t och är därför inte kompatibla med CDA.
* Om din organisation använder det privata diagrammet tar det upp till 24 timmar för nya enheter att sy ihop.
* Nya enheter som besöker webbplatsen kan ta upp till två veckor att bearbetas av Co-op Graph. Symbolnivån i CDA under de senaste två veckorna är vanligtvis lägre än för datumintervall som är äldre än två veckor. Adobe planerar att förbättra Co-op-diagrammet till ett dagligt uppdaterat diagram i framtiden.
* Historiska data i den virtuella rapportsviten ändras baserat på hur Adobe identifierar och sammanfogar enheter. Data i källrapportsviten ändras inte.

När organisationen har uppfyllt alla krav och förstått begränsningarna kan ni börja [konfigurera Cross-Device Analytics](cda-setup.md).
