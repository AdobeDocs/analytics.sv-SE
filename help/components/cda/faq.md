---
title: Vanliga frågor om enhetsövergripande analys
description: Frågor och svar om enhetsövergripande analys
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
translation-type: tm+mt
source-git-commit: 50ffeac17a07478e98e8d83bd3a87db0d9a1145d
workflow-type: tm+mt
source-wordcount: '1670'
ht-degree: 0%

---

# Frågor och svar

## Hur kan jag använda CDA för att se hur människor flyttar från en enhetstyp till en annan?

Du kan använda en [!UICONTROL Flow]-visualisering med dimensionen Mobilenhetstyp.

1. Logga in på Adobe Analytics och skapa ett nytt tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Mobilenhetstyp&quot; till mittplatsen med etiketten &quot;Dimension eller Artikel&quot;.
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

## Kan jag se hur människor rör sig mellan olika användarupplevelser (t.ex. datorwebbläsare jämfört med mobilwebbläsare jämfört med mobilapp)?

Om du använder mobilenhetstyp enligt bilden ovan kan du se hur människor rör sig mellan olika typer av mobila enheter och typer av stationära enheter. Du kanske vill skilja datorwebbläsare från mobilwebbläsare. Ett sätt att göra detta är att skapa en eVar som registrerar om upplevelsen inträffade i en datorwebbläsare, mobilwebbläsare eller mobilapp. Skapa sedan ett flödesdiagram enligt beskrivningen ovan med eVar &quot;experience&quot; i stället för dimensionen Mobile Device Type. Detta ger en något annorlunda vy över beteendet mellan olika enheter.

## Hur långt bak stygger CDA besökare?

CDA:s sammanfogning mellan enheter sker i två samtidiga processer.

* Den första processen kallas för&quot;live stitching&quot;, som inträffar när data strömmar till Adobe Analytics. Under livelösa stygn gör CDA det bästa som kan göras om på personnivå. Men om personen är okänd vid tiden för syning av live, återgår CDA till besökar-ID:t för att representera personen.

* Den andra processen kallas &quot;replay&quot;. Under uppspelning går CDA bakåt i tiden och återställer historiska data, där det är möjligt, inom ett angivet uppslagsfönster. Detta fönster är antingen 1 dag eller 7 dagar, beroende på hur du har begärt att CDA ska konfigureras. Under repriser försöker CDA att skicka tillbaka träffar där personen tidigare var okänd.

* **Om du använder ett enhetsdiagram** behåller Adobe enhetsmappningar i Co-op-diagrammet och det privata diagrammet i ungefär 6 månader. Ett ECID som inte har någon aktivitet på mer än sex månader tas bort från diagrammet. Data som redan sammanfogats i CDA påverkas inte, men efterföljande träffar för detta ECID behandlas som en ny person.

## Hur hanterar CDA tidstämplade träffar?

Adobe behandlar tidsstämplade träffar som om de togs emot vid tidpunkten för tidsstämpeln, inte när Adobe tog emot träffen. Tidsstämplade träffar som är äldre än en månad sammanfogas aldrig eftersom de ligger utanför intervallet som används i Adobe för sammanfogning.

## Hur skiljer sig CDA från anpassade besökar-ID:n?

Att använda ett anpassat besökar-ID är en äldre metod för att [ansluta användare mellan enheter](/help/implement/js/xdevice-visid/xdevice-connecting.md). Med ett anpassat besökar-ID använder du variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md) för att explicit ange det ID som används för besökarlogik. Variabeln `visitorID` åsidosätter alla cookie-baserade ID:n som finns.

Anpassade besökar-ID:n har flera biverkningar som CDA överträffar eller minimerar. Metoden med anpassat besökar-ID har till exempel inga [replay](replay.md)-funktioner. Om en användare autentiseras under ett besök är den första delen av besöket kopplad till ett annat besöks-ID än den senare delen av besöket. De separata besökar-ID:n leder till besöks- och besöksinflammation. CDA omregistrerar historiska data så att oautentiserade träffar tillhör rätt person.

## Kan jag uppgradera från anpassat besökar-ID till CDA?

Kunder som redan använder ett anpassat besökar-ID kan uppgradera till CDA utan implementeringsändringar. Variabeln `visitorID` används fortfarande i källrapportsviten. CDA ignorerar emellertid variabeln `visitorID` i den virtuella rapportsviten om en användare autentiserar.

## Hur hanterar enhetsdiagrammet delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

* **Om du använder ett enhetsdiagram** är möjligheten att hantera delade enheter begränsad. Enhetsdiagrammet använder en algoritm för att fastställa ägarskap för ett kluster och kan ändras varje gång klustret publiceras. Användare av den delade enheten är beroende av vilket kluster de tillhör.
* **Om du använder fältbaserad sammanfogning** åsidosätter det utkast eller den eVar du väljer för att hjälpa till att identifiera inloggade användare andra identifierare. Delade enheter betraktas som separata personer, även om de kommer från samma enhet.

## Hur hanterar CDA situationer där en person har MÅNGA enheter/ECID:n?

I vissa fall kan en enskild användare associera med ett stort antal ECID. Detta kan inträffa om användaren använder många webbläsare eller appar och kan förvärras om de ofta tar bort cookies eller använder webbläsarens privata eller inkodade webbläsarläge.

* **Om du använder ett enhetsdiagram**, anger CDA att antalet ECID som kopplas till ett visst användar-ID ska vara 50. Om ett användar-ID är kopplat till för många ECID:n antar enhetsdiagrammet att användar-ID:t är ogiltigt och tar bort klustret som är kopplat till det användar-ID:t. Användar-ID:t läggs sedan till i en blockeringslista för att förhindra att det läggs till i kluster i framtiden. Resultatet vid rapportering är att användar-ID inte sammanfogas mellan olika enheter.
* **Om du använder fältbaserad sammanfogning** är antalet enheter irrelevanta för det propp/den eVar som du väljer för att hjälpa till att identifiera inloggade användare. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CDA:s möjlighet att sammanfoga enheter.

## Vad är skillnaden mellan personmåttet i CDA och det unika besökarmåttet utanför CDA?

Måttet [Personer](/help/components/metrics/people.md) liknar måttet [Unika besökare](/help/components/metrics/unique-visitors.md) eftersom det rapporterar om antalet unika personer. Men när ni använder enhetsövergripande analys kombineras unika besökare när de annars registreras som två separata unika besökare utanför CDA. Måttet Personer ersätter måttet Unika besökare när Enhetsanalys är aktiverat. Det finns ett nytt mätvärde, [Unika enheter](/help/components/metrics/unique-devices.md), som är ungefär lika med Unika besökare utanför Enhetsanalys.

## Vad är skillnaden mellan måttet &#39;Unika enheter&#39; i CDA och mätvärdet &#39;Unika besökare&#39; utanför CDA?

Dessa två mätvärden är ungefär likvärdiga.

## Kan jag inkludera CDA-värden med API:t 2.0?

Ja. Analysis Workspace använder 2.0-API:t för att begära data från Adobe-servrar, och du kan visa API-anrop som Adobe använder för att skapa egna rapporter:

1. Gå till [!UICONTROL Help] > [!UICONTROL Enable debugger] när du är inloggad på Analysis Workspace.
2. Klicka på felsökningsikonen i den önskade panelen och välj önskad visualisering och tid för begäran.
3. Leta reda på JSON-begäran som du kan använda i API-anropet till Adobe.

## Enhetsövergripande analys kan knyta samman unika besökare. Kan det sy ihop besök tillsammans?

Ja. Om en individ skickar träffar från två separata enheter i din virtuella rapportsvit (30 minuter som standard) sammanfogas de till samma besök.

## Vilket är det ultimata besökar-ID som CDA använder? Kan jag exportera från Adobe Analytics?

* **Om du använder ett enhetsdiagram** är ett anpassat ID baserat på deras kluster den primära identifieraren.
* **Om du använder fältbaserad sammanfogning** är ett anpassat ID baserat på det utkast/den eVar du väljer den primära identifieraren.

Båda dessa identifierare beräknas av Adobe när rapporten körs, och kallas även [Rapporttidsbearbetning](../vrs/vrs-report-time-processing.md). Bearbetningen under rapporttiden innebär att den inte är kompatibel med Data warehouse, dataflöden eller andra exportfunktioner som Adobe erbjuder.

## Hur kan jag gå från enhetsgrafen till fältbaserad sammanfogning, eller vice versa?

Du kan behöva byta från enhetsdiagram till fältbaserad sammanfogning eller vice versa via kundtjänst. Det kan dock ta några veckor eller mer att slutföra en sådan växling och *historiska sammanfogade data från den föregående metoden går förlorade.*

## Hur hanterar Adobe unika gränser för en eVar som används vid fältbaserad sammanfogning?

CDA hämtar dimensionsobjekt för eVar innan de optimeras för rapportering. Ni behöver inte bekymra er om unika gränser för CDA. Om du däremot försökte använda det proffset/eVar i ett Workspace-projekt kan du fortfarande se dimensionsobjektet [(Låg trafik)](/help/technotes/low-traffic.md).

## Hur många av mitt företags rapportsviter kan aktiveras för CDA?

Flera rapportsviter kan vara aktiverade, men varje ytterligare rapportserie ökar den totala provisioneringstiden om flera rapportsviter begärs samtidigt. CDA sammanfogar inte rapportsviter. Varje rapportsvit som har aktiverats för CDA måste vara enhetsövergripande (innehålla data från flera ytor, t.ex. datorwebben, mobilwebben, mobilappar)

## Om min Experience Cloud organisation (även kallad IMS org) har flera företag i olika regioner, kan jag då aktivera CDA för samtliga?

Nej. För samma organisation kan bara en region ha CDA aktiverat.

## Vilka är fördelarna och nackdelarna med en 7-dagars repriser jämfört med en 1-dagars repriser?

Fördelen med 7-dagars uppspelningsfönster är att CDA kan gå tillbaka längre och försöka associera tidigare anonyma händelser med någon som senare loggade in inom dessa 7 dagar. Nackdelarna med 7-dagars uppslagsfönstret är 1) uppspelningen körs endast en gång i veckan och 2) de senaste 7 dagarna kan komma att ändras.

Fördelarna med att använda 1-dagars uppspelningsfönster är 1) uppspelningsomgångar varje dag och 2) endast i går kan komma att ändras. Nackdelen med 1-dagars uppslagsfönstret är att CDA bara kan gå tillbaka en dag för att försöka associera tidigare anonyma händelser med en person som loggade in i går.

## Vad händer med sammanfogade data i mina virtuella CDA-rapporteringsprogram om mitt företag bestämmer sig för att nedgradera från Analytics Ultimate?

Om kunden uppgraderar från Ultimate har de inte längre tillgång till sammansatta data. Alla data som tidigare sammanfogats tas bort. Detta innebär att den virtuella CDA-rapportsviten nu inte kommer att återspegla enhetssammanfogning. Data kommer att se ut ungefär som den ursprungliga osökta rapportsviten.
