---
title: Vanliga frågor om enhetsövergripande analys
description: Frågor och svar om enhetsövergripande analys
translation-type: tm+mt
source-git-commit: 98e09f543381d4a4ac9731a24dbabbf36c94d0a5

---


# Frågor och svar

> [!NOTE] Enhetsövergripande analysdokumentation kan komma att ändras i takt med att funktionen utvecklas ytterligare. Kontrollera regelbundet om det finns uppdateringar.

**Hur kan jag använda CDA för att se hur människor flyttar från en enhetstyp till en annan?**

Du kan använda en Flow-visualisering med mobilenhetstypen.

1. Logga in på Adobe Analytics och skapa ett nytt tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Mobilenhetstyp&quot; till mittplatsen med namnet &quot;Dimension eller Artikel&quot;.
4. Den här flödesrapporten är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

**Kan jag se hur människor rör sig mellan olika användarupplevelser (t.ex. datorwebbläsare jämfört med mobilwebbläsare jämfört med mobilapp)?**

Om du använder mobilenhetstyp enligt bilden ovan kan du se hur människor rör sig mellan olika typer av mobila enheter och typer av stationära enheter. Du kanske vill skilja datorwebbläsare från mobilwebbläsare. Ett sätt att göra detta är att skapa en eVar som registrerar om upplevelsen inträffade i en webbläsare, mobilwebbläsare eller mobilapp. Skapa sedan ett flödesdiagram enligt beskrivningen ovan med&quot;upplevelsen&quot; i eVar i stället för med mobilenhetstypen. Detta ger en något annorlunda vy över beteendet mellan olika enheter.

**Hur långt bak stygger CDA besökare?**

* Adobe lagrar sammanfogade data i cirka 30 dagar. Om en enhet till att börja med inte identifieras av Co-op-diagrammet eller det privata diagrammet, men identifieras senare inom 30 dagar, går CDA tillbaka och anger enheten som identisk person upp till 30 dagar tidigare. Om en del av en användares oidentifierade beteende ligger utanför 30-dagars uppslagsfönstret sammanfogas inte den delen av användarens resa.
* Adobe sparar enhetsmappningar i Co-op Graph och Private Graph i ungefär 6 månader. Ett ECID som inte har någon aktivitet på mer än sex månader tas bort från diagrammet. Data som redan sammanfogats i CDA påverkas inte, men efterföljande träffar för detta ECID behandlas som en ny individ.

**Hur hanterar CDA tidstämplade träffar?**

Adobe behandlar tidsstämplade träffar som om de togs emot vid tidpunkten för tidsstämpeln, inte när Adobe fick träffen. Tidsstämplade träffar som är äldre än en månad kan inte sammanfogas eftersom de ligger utanför det intervall som Adobe lagrar data som används för sammanfogning.

**Hur skiljer sig CDA från anpassade besökar-ID:n?**

[Anpassat besökar-ID](/help/implement/vars/config-vars/visitorid.md) är en äldre metod för att [ansluta användare till olika enheter](/help/implement/js/xdevice-visid/xdevice-connecting.md). Med ett anpassat besökar-ID använder du variabeln för att explicit ange det ID som används för besökarlogik. `s.visitorID` Variabeln åsidosätter alla cookie-baserade ID:n som finns. `s.visitorID`

Anpassade besökar-ID:n har flera biverkningar som CDA överträffar eller minimerar. Metoden med anpassat besökar-ID har till exempel inga uppslagsfunktioner. Om en användare autentiseras under ett besök är den första delen av besöket kopplad till ett annat besöks-ID än den senare delen av besöket. De separata besökar-ID:n leder till besöks- och besöksinflammation. CDA:s 30-dagars uppslagsfönster gör det möjligt att gå bakåt i tiden för att ange om tidigare beteenden tillhör samma person, vilket medför oautentiserat enhetsövergripande beteende tillsammans med autentiserat enhetsövergripande beteende med noll eller minimal uppblåsning.

**Kan jag uppgradera från anpassat besökar-ID till CDA?**

Kunder som redan använder ett anpassat besökar-ID kan uppgradera till CDA. Det `s.visitorID` åsidosätter fortfarande de underliggande cookie-baserade ID:n i basrapportsviten. Men i den virtuella rapportsviten ignorerar CDA `s.visitorID` för enheter som identifieras av enhetsdiagrammet.

**Hur hanterar enhetsdiagrammet delade enheter?**

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag. I dessa fall synkroniseras ID:t till enhetsdiagrammet från dessa delade enheter och anger att flera användare associerar med den enheten över tiden. Enhetsdiagrammet (vare sig det är Co-op eller privat diagram) länkar inte ECID på enheten till någon av dessa användare. I stället länkar diagrammet ECID:t till ett kluster som innehåller alla associerade användare. Diagrammet försöker hålla klustret så stabilt som möjligt i stället för att kontinuerligt växla mellan kluster med ECID. Därför kan inte CDA skilja mellan enskilda användare på en delad enhet. Alla användare av den delade enheten betraktas som en enda person i CDA.

**Hur hanterar enhetsdiagrammet situationer där en person har MÅNGA enheter/ECID:n?**

I vissa fall kan en enskild användare associera med ett stort antal ECID. Detta kan inträffa om användaren använder många webbläsare eller appar och kan förvärras om de ofta tar bort cookies eller använder webbläsarens privata eller inkodade webbläsarläge. Enhetsdiagrammet begränsar antalet ECID:n som kopplas till ett visst användar-ID till 200. Om ett användar-ID är kopplat till för många ECID:n antar enhetsdiagrammet att användar-ID:t är ogiltigt och tar bort klustret som är kopplat till det användar-ID:t. Användar-ID:t blir sedan svartlistat så att det inte längre blir en ny gruppering. Resultatet i CDA är att användar-ID:ts beteende inte sammanfogas mellan olika enheter.

**Vad är skillnaden mellan personmåttet i CDA och det unika besökarmåttet utanför CDA?**

Måttet Personer liknar det för unika besökare i och med att det rapporterar antalet unika personer. Men när ni använder enhetsövergripande analys kombineras unika besökare när de annars registreras som två separata unika besökare utanför CDA. Måttet Personer ersätter måttet Unika besökare när Analytics för olika enheter är aktiverat.

**Vad är skillnaden mellan måttet &#39;Unika enheter&#39; i CDA och mätvärdet &#39;Unika besökare&#39; utanför CDA?**

Dessa två mätvärden är ungefär likvärdiga.

**Kan jag inkludera CDA-värden med API:t 2.0?**

Ja. Analysis Workspace använder 2.0-API:t för att begära data från Adobes servrar, och du kan visa API-anrop som Adobe använder för att skapa egna rapporter:

1. När du är inloggad på Analysis Workspace öppnar du webbläsarens utvecklarverktyg (F12 för de flesta webbläsare).
1. Skriv `adobeTools.showDebugger()`i webbläsarkonsolen. Sidan läses in igen med felsökningsikoner i det övre högra hörnet av varje panel.
1. Klicka på felsökningsikonen i den önskade panelen och välj önskad visualisering och tid för begäran.
1. Leta reda på JSON-begäran som du kan använda i API-anropet till Adobe.

**Enhetsövergripande analys kan knyta samman unika besökare. Kan den sätta ihop besök?**

Ja. Om en individ skickar träffar från två separata enheter i din virtuella rapportsvit (30 minuter som standard) sammanfogas de till samma besök.

**Vilket är det ultimata besökar-ID som CDA använder? Kan jag exportera den från Adobe Analytics?**

Enhetsövergripande analys beräknar sammanfogade data med hjälp av ett kluster-ID. Identifieraren beräknas av Adobe när rapporten körs och kallas även Rapporttidsbearbetning. Bearbetningen under rapporttid innebär att den inte är kompatibel med datalager, dataflöden eller andra exportfunktioner som Adobe erbjuder.
