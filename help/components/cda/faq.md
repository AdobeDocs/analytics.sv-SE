---
title: Vanliga frågor om enhetsövergripande analys
description: Frågor och svar om enhetsövergripande analys
translation-type: tm+mt
source-git-commit: a46b68c7e4ea82b31ed400bf3e6180a7358bb3b5
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---


# Frågor och svar

## Hur kan jag använda CDA för att se hur människor flyttar från en enhetstyp till en annan?

Du kan använda en Flow-visualisering med mobilenhetstypen.

1. Logga in på Adobe Analytics och skapa ett nytt tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Mobilenhetstyp&quot; till mittplatsen med etiketten &quot;Dimension eller Artikel&quot;.
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

## Kan jag se hur människor rör sig mellan olika användarupplevelser (t.ex. datorwebbläsare jämfört med mobilwebbläsare jämfört med mobilapp)?

Om du använder mobilenhetstyp enligt bilden ovan kan du se hur människor rör sig mellan olika typer av mobila enheter och typer av stationära enheter. Du kanske vill skilja datorwebbläsare från mobilwebbläsare. Ett sätt att göra detta är att skapa en eVar som registrerar om upplevelsen inträffade i en datorwebbläsare, mobilwebbläsare eller mobilapp. Skapa sedan ett flödesdiagram enligt beskrivningen ovan med eVar &quot;experience&quot; i stället för dimensionen Mobile Device Type. Detta ger en något annorlunda vy över beteendet mellan olika enheter.

## Hur långt bak stygger CDA besökare?

Adobe behåller data för att fästa enheten i cirka 30 dagar. Om en enhet till att börja med inte identifieras, men identifieras senare inom 30 dagar, går CDA tillbaka och uppger att enheten tillhör den identifierade personen upp till 30 dagar tidigare. Om en del av en användares oidentifierade beteende ligger utanför 30-dagars uppslagsfönstret sammanfogas inte den delen av användarens resa.

* **Om du använder ett enhetsdiagram** behåller Adobe enhetsmappningar i Co-op-diagrammet och det privata diagrammet i ungefär 6 månader. Ett ECID som inte har någon aktivitet på mer än sex månader tas bort från diagrammet. Data som redan sammanfogats i CDA påverkas inte, men efterföljande träffar för detta ECID behandlas som en ny person.

## Hur hanterar CDA tidstämplade träffar?

Adobe behandlar tidsstämplade träffar som om de togs emot vid tidpunkten för tidsstämpeln, inte när Adobe tog emot träffen. Tidsstämplade träffar som är äldre än en månad sammanfogas aldrig eftersom de ligger utanför intervallet som används i Adobe för sammanfogning.

## Hur skiljer sig CDA från anpassade besökar-ID:n?

Att använda ett anpassat besökar-ID är en äldre metod för att [ansluta användare till olika enheter](/help/implement/js/xdevice-visid/xdevice-connecting.md). Med ett anpassat besökar-ID använder du variabeln för att explicit ange det ID som används för besökarlogik. [`visitorID`](/help/implement/vars/config-vars/visitorid.md) Variabeln åsidosätter alla cookie-baserade ID:n som finns. `visitorID`

Anpassade besökar-ID:n har flera biverkningar som CDA överträffar eller minimerar. Metoden med anpassat besökar-ID har till exempel inga [repriser](replay.md) . Om en användare autentiseras under ett besök är den första delen av besöket kopplad till ett annat besöks-ID än den senare delen av besöket. De separata besökar-ID:n leder till besöks- och besöksinflammation. CDA omregistrerar historiska data så att oautentiserade träffar tillhör rätt person.

## Kan jag uppgradera från anpassat besökar-ID till CDA?

Kunder som redan använder ett anpassat besökar-ID kan uppgradera till CDA utan implementeringsändringar. Variabeln `visitorID` används fortfarande i källrapportsviten. CDA ignorerar dock variabeln `visitorID` i den virtuella rapportsviten om en användare autentiserar.

## Hur hanterar enhetsdiagrammet delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

* **Om du använder ett enhetsdiagram**&#x200B;är möjligheten att hantera delade enheter begränsad. Enhetsdiagrammet använder en algoritm för att fastställa ägarskap för ett kluster och kan ändras varje gång klustret publiceras. Användare av den delade enheten är beroende av vilket kluster de tillhör.
* **Om du använder fältbaserad sammanfogning**&#x200B;åsidosätter det utkast eller den eVar du väljer för att hjälpa till att identifiera inloggade användare andra identifierare. Delade enheter betraktas som separata personer, även om de kommer från samma enhet.

## Hur hanterar CDA situationer där en person har MÅNGA enheter/ECID:n?

I vissa fall kan en enskild användare associera med ett stort antal ECID. Detta kan inträffa om användaren använder många webbläsare eller appar och kan förvärras om de ofta tar bort cookies eller använder webbläsarens privata eller inkodade webbläsarläge.

* **Om du använder ett enhetsdiagram**, anger CDA att antalet ECID som kopplas till ett visst användar-ID ska vara 50. Om ett användar-ID är kopplat till för många ECID:n antar enhetsdiagrammet att användar-ID:t är ogiltigt och tar bort klustret som är kopplat till det användar-ID:t. Användar-ID:t läggs sedan till i en blockeringslista för att förhindra att det läggs till i kluster i framtiden. Resultatet vid rapportering är att användar-ID inte sammanfogas mellan olika enheter.
* **Om du använder fältbaserad sammanfogning**&#x200B;är antalet enheter irrelevanta för det propp/den eVar som du väljer för att hjälpa till att identifiera inloggade användare. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CDA:s möjlighet att sammanfoga enheter.

## Vad är skillnaden mellan personmåttet i CDA och det unika besökarmåttet utanför CDA?

Mätvärdet för [Personer](/help/components/metrics/people.md) liknar det för [unika besökare](/help/components/metrics/unique-visitors.md) i och med att det rapporterar antalet unika individer. Men när ni använder enhetsövergripande analys kombineras unika besökare när de annars registreras som två separata unika besökare utanför CDA. Måttet Personer ersätter måttet Unika besökare när Analytics för olika enheter är aktiverat.

## Vad är skillnaden mellan måttet &#39;Unika enheter&#39; i CDA och mätvärdet &#39;Unika besökare&#39; utanför CDA?

Dessa två mätvärden är ungefär likvärdiga.

## Kan jag inkludera CDA-värden med API:t 2.0?

Ja. Analysis Workspace använder 2.0-API:t för att begära data från Adobe-servrar, och du kan visa API-anrop som Adobe använder för att skapa egna rapporter:

1. När du är inloggad på Analysis Workspace går du till [!UICONTROL Help] > [!UICONTROL Enable debugger].
2. Klicka på felsökningsikonen i den önskade panelen och välj önskad visualisering och tid för begäran.
3. Leta reda på JSON-begäran som du kan använda i API-anropet till Adobe.

## Enhetsövergripande analys kan knyta samman unika besökare. Kan det sy ihop besök tillsammans?

Ja. Om en individ skickar träffar från två separata enheter i din virtuella rapportsvit (30 minuter som standard) sammanfogas de till samma besök.

## Vilket är det ultimata besökar-ID som CDA använder? Kan jag exportera från Adobe Analytics?

* **Om du använder ett enhetsdiagram**&#x200B;är ett anpassat ID baserat på deras kluster den primära identifieraren.
* **Om du använder fältbaserad sammanfogning**&#x200B;är ett anpassat ID baserat på det utkast/den eVar du väljer den primära identifieraren.

Båda dessa identifierare beräknas av Adobe vid den tidpunkt då rapporten körs, vilket också kallas [rapporttidsbearbetning](../vrs/vrs-report-time-processing.md). Bearbetningen under rapporttiden innebär att den inte är kompatibel med Data warehouse, dataflöden eller andra exportfunktioner som Adobe erbjuder.

## Hur kan jag gå från enhetsgrafen till fältbaserad sammanfogning, eller vice versa?

Om du vill byta CDA-identifieringsmetod ska du prata med din organisations Account Manager. Kontohanteraren kan distribuera din rapportsserie till den metod du vill använda för att identifiera personer. *Historiska sammanfogade data från föregående metod går förlorade.*

## Hur hanterar Adobe unika gränser för en eVar som används vid fältbaserad sammanfogning?

CDA hämtar dimensionsobjekt för eVar innan de optimeras för rapportering. Ni behöver inte bekymra er om unika gränser för CDA. Om du däremot har försökt använda detta utkast/eVar i ett Workspace-projekt kan du fortfarande se dimensionsobjektet [(Låg trafik)](/help/technotes/low-traffic.md) .
