---
title: Vanliga frågor om enhetsövergripande analys
description: Vanliga frågor och svar om enhetsövergripande analys
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '1949'
ht-degree: 0%

---


# Frågor och svar

{{available-existing-customers}}

+++ Hur kan jag använda CDA för att se hur människor flyttar från en enhetstyp till en annan?

Du kan använda en [!UICONTROL Flow]-visualisering med dimensionen för mobilenhetstyp.

1. Logga in på Adobe Analytics och skapa ett nytt tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Mobilenhetstyp&quot; till mittplatsen med etiketten &quot;Dimension eller Artikel&quot;.
4. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

+++

+++ Kan jag se hur människor rör sig mellan olika användarupplevelser (till exempel webbläsare på stationära datorer jämfört med mobilwebbläsare jämfört med mobilappar)?

I exemplet med mobilenhetstyp ovan kan du se hur människor rör sig mellan olika typer av mobila enheter och typer av stationära enheter. Du kan dock inte skilja datorwebbläsare från mobilwebbläsare. Om du vill ha den här informationen kan du skapa en anpassad variabel (till exempel ett utkast eller en eVar) som registrerar om upplevelsen inträffar i en datorwebbläsare, mobilwebbläsare eller mobilapp. Du kan sedan skapa ett flödesdiagram enligt beskrivningen ovan med den anpassade variabeln i stället för mobilenhetstypen. Den här metoden ger en något annorlunda vy över beteendet mellan olika enheter.

+++

+++ Hur långt bak stygger CDA besökare?

CDA:s sammanfogning mellan enheter sker i två samtidiga processer.

* Den första processen kallas för&quot;live stitching&quot;, som inträffar när data strömmar till Adobe Analytics. Under livelösa stygn gör CDA det bästa som kan göras om på personnivå. Men om personen är okänd vid tiden för syning av live, återgår CDA till besökar-ID:t för att representera personen.

* Den andra processen kallas &quot;replay&quot;. Under uppspelning går CDA bakåt i tiden och återställer historiska data, där det är möjligt, inom ett angivet uppslagsfönster. Detta fönster är antingen 1 dag eller 7 dagar, beroende på hur du har begärt att CDA ska konfigureras. Under repriser försöker CDA att skicka tillbaka träffar där personen tidigare var okänd.

* **Om du använder ett enhetsdiagram** behåller Adobe Device Graph-mappningar i ungefär 6 månader. Ett ECID som inte har någon aktivitet på mer än sex månader tas bort från diagrammet. Data som redan sammanfogats i CDA påverkas inte. Efterföljande träffar för detta ECID behandlas som en ny person.

+++

+++ Hur hanterar CDA tidstämplade träffar?

Adobe behandlar tidsstämplade träffar som om de togs emot vid tidpunkten för tidsstämpeln, inte när Adobe tog emot träffen. Tidsstämplade träffar som är äldre än en månad sammanfogas aldrig eftersom de ligger utanför intervallet som används i Adobe för sammanfogning.

+++

+++ Hur skiljer sig CDA från anpassade besökar-ID:n?

Att använda ett anpassat besökar-ID är en äldre metod för att [ansluta användare mellan enheter](/help/implement/js/xdevice-visid/xdevice-connecting.md). Med ett anpassat besökar-ID använder du variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md) för att explicit ange det ID som används för besökslogik. Variabeln `visitorID` åsidosätter alla cookie-baserade ID:n som finns.

Anpassade besökar-ID har flera biverkningar som CDA överträffar eller minimerar. Metoden för anpassat besökar-ID har till exempel inga [replay](replay.md)-funktioner. Om en användare autentiseras under ett besök är den första delen av besöket kopplad till ett annat besöks-ID än den senare delen av besöket. De separata besökar-ID:n leder till besöks- och besöksinflammation. CDA omregistrerar historiska data så att oautentiserade träffar tillhör rätt person.

+++

+++ Kan jag uppgradera från anpassat besökar-ID till CDA?

Kunder som redan använder ett anpassat besökar-ID kan uppgradera till CDA utan implementeringsändringar. Variabeln `visitorID` används fortfarande i källrapportsviten. CDA ignorerar dock variabeln `visitorID` i den virtuella rapportsviten om en användare autentiserar.

+++

+++ Hur hanterar enhetsdiagrammet delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

* **Om du använder ett enhetsdiagram** är möjligheten att hantera delade enheter begränsad. Enhetsdiagrammet använder en algoritm för att fastställa ägarskap för ett kluster och kan ändras varje gång klustret publiceras. Användare av den delade enheten är beroende av vilket kluster de tillhör.
* **Om du använder fältbaserad sammanfogning** åsidosätter det utkast eller den eVar som du väljer för att hjälpa till att identifiera inloggade användare andra identifierare. Delade enheter betraktas som separata personer, även om de kommer från samma enhet.

+++

+++ Hur hanterar CDA situationer där en person har MÅNGA enheter/ECID:n?

I vissa fall kan en enskild användare associera med ett stort antal ECID. Detta kan inträffa om användaren använder många webbläsare eller appar och kan förvärras om de ofta tar bort cookies eller använder webbläsarens privata eller inkodade webbläsarläge.

* **Om du använder ett enhetsdiagram** anger CDA att antalet ECID:n som är kopplade till ett visst användar-ID ska vara 50. Om ett användar-ID är kopplat till för många ECID:n antar enhetsdiagrammet att användar-ID:t är ogiltigt och tar bort klustret som är kopplat till det användar-ID:t. Användar-ID:t läggs sedan till i en blockeringslista för att förhindra att det läggs till i kluster i framtiden. Resultatet vid rapportering är att användar-ID inte sammanfogas mellan olika enheter.
* **Om du använder fältbaserad sammanfogning** är antalet enheter irrelevanta för det prop/den eVar som du väljer för att hjälpa till att identifiera inloggade användare. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CDA:s möjlighet att sammanfoga enheter.

+++

+++ Vad är skillnaden mellan personmåttet i CDA och det unika besökarmåttet utanför CDA?

Mätvärdena för både [Personer](/help/components/metrics/people.md) och [Unika besökare](/help/components/metrics/unique-visitors.md) syftar till att räkna distinkta besökare (personer). Tänk dock på möjligheten att två olika enheter kan tillhöra samma person. CDA mappar de två enheterna till samma person, medan de två enheterna registreras som två separata &#39;Unika besökare&#39; utanför CDA.

+++

+++ Vad är skillnaden mellan måttet &#39;Unika enheter&#39; i CDA och mätvärdet &#39;Unika besökare&#39; utanför CDA?

Dessa två mätvärden är ungefär likvärdiga. Skillnader mellan de två måtten uppstår när:

* En delad enhet mappar till flera personer. I det här scenariot räknas en unik besökare, medan flera unika enheter räknas.
* En enhet har både icke-sammansatt och sammansatt trafik från samma besökare. En webbläsare genererade till exempel identifierad sammanfogad trafik + historik anonym trafik som inte sammanfogats. I det här fallet räknas 1 unik besökare, medan 2 unika enheter räknas.

Se [Unika enheter](/help/components/metrics/unique-devices.md) för fler exempel och mer information om hur det fungerar.

+++

+++ Kan jag inkludera CDA-värden med Adobe Analytics 2.0 API?

Ja. Analysis Workspace använder 2.0-API:t för att begära data från Adobe-servrar, och du kan visa API-anrop som Adobe använder för att skapa egna rapporter:

1. Gå till [!UICONTROL Help] > [!UICONTROL Enable debugger] när du är inloggad på Analysis Workspace.
2. Klicka på felsökningsikonen i den önskade panelen och välj önskad visualisering och tid för begäran.
3. Leta reda på JSON-begäran som du kan använda i API-anropet till Adobe.

+++

+++ Enhetsövergripande analys kan knyta samman unika besökare. Kan det sy ihop besök tillsammans?

Ja. Om en individ skickar träffar från två separata enheter i din virtuella rapportsvit (30 minuter som standard) sammanfogas de till samma besök.

+++

+++ Vilket är det ultimata besökar-ID som CDA använder? Kan jag exportera den från Adobe Analytics?

* **Om du använder ett enhetsdiagram** är ett anpassat ID baserat på deras kluster den primära identifieraren.
* **Om du använder fältbaserad sammanfogning** är ett anpassat ID baserat på den profil/eVar du väljer den primära identifieraren.

Båda dessa identifierare beräknas av Adobe vid den tidpunkt då rapporten körs, vilket också kallas [Rapporttidsbearbetning](../vrs/vrs-report-time-processing.md). Bearbetningen under rapporttiden innebär att den inte är kompatibel med Data Warehouse, dataflöden eller andra exportfunktioner som Adobe erbjuder.

+++

+++ Hur kan jag gå från enhetsgrafen till fältbaserad sammanfogning, eller vice versa?

Du kan behöva byta från enhetsdiagram till fältbaserad sammanfogning eller vice versa via kundtjänst. Det kan dock ta några veckor eller mer att slutföra en sådan växling och *historiska sammanfogade data från den tidigare metoden går förlorade.*

+++

+++ Hur hanterar Adobe unika gränser för ett prop eller en eVar som används vid fältbaserad sammanfogning?

CDA hämtar identifierarvariabeldimensionsobjekten innan de optimeras för rapportering. Ni behöver inte bekymra er om unika gränser för CDA. Om du däremot har försökt använda detta utkast eller eVar i ett Workspace-projekt kan du fortfarande se dimensionsobjektet [(låg trafik)](/help/technotes/low-traffic.md).

+++

+++ Hur många av mitt företags rapportsviter kan aktiveras för CDA?

Från och med den 1 maj 2022 kommer all ny implementering av CDA att begränsas till högst tre RSID:er (Report Suite ID) per kund. CDA sammanfogar inte rapportsviter. Varje rapportsvit som har aktiverats för CDA måste vara enhetsövergripande (innehålla data från flera ytor, t.ex. datorwebben, mobilwebben, mobilappar).

+++

+++ Om mitt organisations-ID har flera företag i olika regioner, kan jag aktivera CDA för alla dessa?

Nej. För samma organisations-ID kan bara en region ha CDA aktiverat.

+++

+++ Vilka är fördelarna och nackdelarna med en 7-dagars repriser jämfört med en 1-dagars repriser?

Fördelen med 7-dagars uppspelningsfönster är att CDA kan gå tillbaka längre och försöka associera tidigare anonyma händelser med någon som senare loggade in inom dessa 7 dagar. Nackdelarna med 7-dagars uppslagsfönstret är 1) uppspelningen körs endast en gång i veckan och 2) de senaste 7 dagarna kan komma att ändras.

Fördelarna med att använda 1-dagars uppspelningsfönster är 1) uppspelningsomgångar varje dag och 2) endast i går kan komma att ändras. Nackdelen med 1-dagars uppslagsfönstret är att CDA bara kan gå tillbaka en dag för att försöka associera tidigare anonyma händelser med en person som loggade in i går.

+++

+++ Vad händer med sammanfogade data i mina virtuella CDA-rapporteringsprogram om mitt företag bestämmer sig för att nedgradera från Analytics Ultimate?

Om en kund nedgraderar från Ultimate har de inte längre tillgång till sammansatta data. Alla data som tidigare sammanfogats tas bort. Detta innebär att den virtuella CDA-rapportsviten nu inte kommer att återspegla enhetssammanfogning. Data kommer att se ut ungefär som det ursprungliga osökta rapportpaketet.

+++

+++ Varför skiljer det totala antalet träffar mellan min källrapportsserie och den virtuella CDA-rapportsviten?

CDA använder en komplex parallell bearbetningsprocess, med flera beroende komponenter. Ett datamatchningsfel på ungefär 1 % för det totala antalet träffar mellan den ursprungliga rapportsviten och den virtuella CDA-rapportsviten förväntas.

+++

+++ Varför inflateras mätvärdet &#39;Identified People&#39;?

Antalet identifierade personer kan vara något högre om värdet för identifieraren prop/eVar körs i en [hash-kollision](/help/implement/validate/hash-collisions.md).

För fältbaserad sammanfogning är den anpassade variabeln för identifierare skiftlägeskänslig. Antalet identifierade personer kan vara betydligt högre om identifierarvärdena inte matchar gemener/VERSALER. Om till exempel `bob` och `Bob` skickas och förväntas vara samma person tolkar CDA dessa två värden som distinkta.

+++

+++ När jag tittar på identifieraruttrycket/eVarna, varför ser jag värden som inte är noll för mätvärdet &#39;Ej identifierade personer&#39;?

Detta inträffar vanligtvis när en besökare genererar både autentiserade och oautentiserade träffar i rapportfönstret. Besökaren tillhör både &#39;Oidentifierad&#39; och &#39;Identifierad&#39; i dimensionen [Identifierad status](/help/components/dimensions/identified-state.md), vilket ger en attribuering av oidentifierade träffar till en identifierare. Det här scenariot kan ändras efter att [Replay](replay.md) har körts, beroende på återspelningsfrekvens och slutförandefrekvens.

+++
