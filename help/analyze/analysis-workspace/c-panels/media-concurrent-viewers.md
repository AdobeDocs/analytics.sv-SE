---
title: Panelen Samtidiga visningsprogram
description: Så här använder och tolkar du panelen Samtidiga visningsprogram i Analysis Workspace.
translation-type: tm+mt
source-git-commit: 807c5e31b376799f4494ecc24cebfd9498c39e63
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 0%

---


# Panelen Samtidiga visningsprogram

>[!IMPORTANT]
>
>Den här funktionen är i en fasad lansering för Media Analytics-kunder.

Media Analytics-kunder kan analysera samtidiga tittare för att förstå var maximal samtidighet har inträffat eller var bortfall har skett för att ge värdefull insikt i kvaliteten på innehåll och tittarengagemang och för att hjälpa till med felsökning eller planering av volym eller skala.

I Analysis Workspace är Concurrent Viewers antalet unika besökare som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.

Med Media Concurrent Viewers-panelen kan man analysera samtidiga visningsprogram över tiden, med detaljer om maximal samtidighet och möjlighet att dela upp och jämföra.  Om du vill få åtkomst till panelen Medievisningsprogram för samtidiga media går du till en rapportsvit med Media Analytics-komponenter aktiverade. Klicka sedan på panelikonen längst till vänster och dra panelen till ditt Analysis Workspace-projekt.

## Panelindata {#Input}

Du kan konfigurera panelen Medievisningsprogram för samtidig användning med dessa indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Panelens datumintervall | Panelens datumintervall är som standard Idag.  Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br> <br> Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Kornighet | Granularitetsstandardvärdet är Minut. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Sammanfattningsnummer för panel | Det finns en sammanfattning av datum- och tidsinformation för samtidiga visningsprogram. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet.  Som standard visas bara Maximum, men du kan ändra den till Minimum eller både Maximum och Minimum.<br><br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| Uppdelning efter serie | Du kan även dela upp visualiseringen efter segment, dimensioner, dimensionsobjekt eller datumintervall. <br><br>- Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br><br>- När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.<br><br>- Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |

### Standardvy

![Standardvy](assets/concurrent-viewers-default.png)


### Serieuppdelad vy

![serieuppdelad vy](assets/concurrent-viewers-series-breakdown.png)

## Panelutdata {#Output}

Panelen Media Concurrent Viewer returnerar ett linjediagram och sammanfattningsnummer som innehåller information om maximalt och/eller lägsta antal samtidiga visningsprogram.  Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Du kan när som helst redigera och återskapa panelen genom att klicka på redigeringspennan längst upp till höger.

Om du har valt seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![samtidiga visningsprogram](assets/concurrent-viewers-output.png)

### Datakälla

Det enda mätvärdet som kan användas i den här panelen är samtidiga visningsprogram:

| Mått | Beskrivning |
|---|---|
| Samtidiga visningsprogram | Antal unika besökare som visar medieströmmar vid en viss tidpunkt, oavsett antalet sessioner.<br><br>Detta skiljer sig från Concurrent Viewer-rapporteringen i avsnittet Rapporter, där Concurrent Active Sessions används.  Använda unika besökskonton för att ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |

Det finns ingen friformstabell i den här vyn.  Om du vill visa datakällan kan du högerklicka på linjediagrammet och hämta som en CSV-fil.  Serieuppdelningar inkluderas.


![samtidiga visningsprogram](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | Frihandsregistret är inte tillgängligt i den här vyn.  Du kan hämta datakällan genom att högerklicka på linjediagrammet och hämta CSV-filen. |
| Varför ändrades min granularitet? | Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.<br><br>Om du ändrar från ett större datumintervall till ett mindre kommer granulariteten att uppdateras till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den. |
| Hur jämför jag videonamn, segment, innehållstyper osv.? | Om du vill jämföra dessa i en enda visualisering drar du segment, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.<br><br>Vyn är begränsad till tio uppdelningar.  Om du vill visa mer än 10 måste du använda flera paneler. |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall.  Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | På den här panelen kan du endast använda linjevisualisering för tidsserien. |
| Kan jag köra avvikelseidentifiering? | Nej.  Anomalsidentifiering är inte tillgängligt för den här panelen. |
| Varför använda unika besökare istället för aktiva sessioner? | Genom att använda unika besökare kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |
| Vad innebär det att ha samtidiga visningsprogram med högre granularitet än en minut? | Med en granularitet som är större än en minut är samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom det tidsintervallet.  På timnivå är till exempel samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom timmen. |
| Vad gör jag om jag vill se mer än en dag i granularitet på minutnivå? | Om du vill få åtkomst till data på minutnivå i upp till en månad i taget kan du använda API:t för analysrapportering (2.0 eller 1.4). Mer information om API:er för Analytics finns i [Analytics API Reports User Guide](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
