---
title: Medieuppspelningstid spenderad panel
description: Så här använder och tolkar du panelen Medieuppspelningstid för spenderad tid i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 6347601c5c1b8e84f37db308717799dea43bd26d
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 0%

---

# Medieuppspelningstid spenderad panel

Media Analytics-kunder kan analysera den uppspelningstid som använts för att förstå var maximal samtidighet inträffade eller var bortfall inträffade för att ge värdefull insikt i innehållets och visningsprogrammets kvalitet och för att hjälpa till med felsökning eller planering av volym eller skala.

Här är en videoöversikt av panelen:

>[!VIDEO](https://video.tv.adobe.com/v/338699/?quality=12&learn=on)

I Analysis Workspace är uppspelningstid den tid som du har lagt på att visa medieströmmar vid en viss tidpunkt, och omfattar paus, buffert och tid till start.

Med panelen Medieuppspelningstid för spenderad kan du analysera uppspelningen över tid, med detaljer om maximal samtidighet och möjlighet att bryta ned och jämföra. Om du vill komma åt panelen Medieuppspelningstid för spenderad navigerar du till en rapportsvit med Media Analytics-komponenter aktiverade. Klicka sedan på panelikonen längst till vänster och dra panelen till ditt Analysis Workspace-projekt.

Panelen innehåller även nya funktioner i kalendern som gör att du kan markera och visa mindre än 24 timmar. Du kan göra det för hela panelen, eller så kan du skapa segment med hjälp av sammanhängande tidsperioder så att du kan spåra inledande/utledande visning för olika program eller avsnitt i program. När du har placerat minst två av datumsegmenten visas en alternativknapp för Datumsekvensvisning som antingen täcker raderna med en gemensam start på x-axeln eller visar dem i ordning med den specifika starten på x-axeln.

## Panelindata {#Input}

Du kan konfigurera panelen Tid för uppspelning av media med följande indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Panelens datumintervall | Panelens datumintervall är som standard Idag. Du kan redigera den för att visa en enstaka dag eller flera månader i taget.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Kornighet | Granularitetsstandardvärdet är Minut.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Sammanfattningsnummer för panel | Om du vill visa datum- eller tidsinformation för uppspelningstid finns ett sammanfattningsnummer. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet. Summan lägger ihop den totala uppspelningstiden för markeringen. Panelens standardinställning visar bara Maximum, men du kan ändra den till Minimal, Summa eller valfri kombination av de tre.<br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| Uppdelning efter serie | Du kan även dela upp visualiseringen efter segment, dimensioner, dimensionsobjekt eller datumintervall.<p>- Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.</p><p>- När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.</p>- Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |
| Tidsformat | Du kan visa uppspelningstiden i båda timmarna:Minutes:Sekunder (standard) eller i minuter (som visas i heltal, avrundat uppåt till 0,5). |
| Visning av datumsekvens | Om du har placerat minst två datumintervallsegment som serieuppdelningar visas alternativet att välja antingen övertäckning (standard) eller sekventiell. Med Övertäckning visas raderna med en gemensam x-axelstart så att de körs parallellt, medan linjer visas sekventiellt med den specifika x-axelstarten. Om dataraderna är i linje (t.ex. segment 1 slutar vid 20:44 och segment 2 börjar vid 20:45) visas raderna i följd. |

### Standardvy

![Standardvy](assets/mpts_default_view.png)

## Panelutdata {#Output}

På panelen Medieuppspelningstid för spenderad tid returneras ett linjediagram och sammanfattningsnummer som innehåller information om den maximala, minimala och/eller sammanlagda uppspelningstiden. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Du kan när som helst redigera och återskapa panelen genom att klicka på redigeringspennan längst upp till höger.

Om du har valt seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![mediespelningstid för utdata](assets/mpts_outputs1.png)

### Datakälla

Det enda mätvärdet som kan användas i den här panelen är Använd uppspelningstid.

| Mått | Beskrivning |
|---|---|
| Antal uppspelningstider | Totalt antal timmar:minutes:sekunder (eller minuter) av innehåll som visas under den valda granulariteten, inklusive paus, buffert och tid till start. |

## Vanliga frågor {#FAQ}

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | <p></p><p>Frihandsregistret är inte tillgängligt i den här vyn. Du kan hämta datakällan genom att högerklicka på linjediagrammet och hämta CSV-filen.</p> |
| <p>Varför ändrades min granularitet?</p> | <p>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.</p><p></p><p>Om du ändrar från ett större datumintervall till ett mindre kommer granulariteten att uppdateras till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den.</p> |
| <p></p><p>Hur jämför jag videonamn, segment, innehållstyper osv.?</p> | <p>Om du vill jämföra dessa i en enda visualisering drar du segment, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.</p><p></p><p>Vyn är begränsad till tio uppdelningar. Om du vill visa mer än 10 måste du använda flera paneler.</p> |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall. Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | <p></p><p>På den här panelen kan du endast använda linjevisualisering för tidsserien.</p> |
| Kan jag köra avvikelseidentifiering? | <p></p><p>Nej. Anomalsidentifiering är inte tillgängligt för den här panelen.</p> |
