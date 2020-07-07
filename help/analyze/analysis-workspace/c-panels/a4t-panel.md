---
description: På panelen Analytics för Target (A4T) kan du analysera dina Adobe Target aktiviteter och upplevelser i Analysis Workspace.
title: Panelen Analytics för Target (A4T)
translation-type: tm+mt
source-git-commit: f9190c15da2d94b3c9006f973fa4aef92162ff04
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 2%

---


# Panelen Analytics för Target (A4T)

På panelen Analytics för Target (A4T) kan du analysera dina Adobe Target aktiviteter och upplevelser i Analysis Workspace. Det gör det också möjligt för er att se hur ni lyfter och litar på upp till tre framgångsvärden. Om du vill komma åt A4T-panelen går du till en rapportsvit där A4T-komponenter är aktiverade. Klicka sedan på panelikonen längst till vänster och dra panelen Analytics för Target till Analysis Workspace-projektet.

## Panelindata {#Input}

Du kan konfigurera A4T-panelen med följande indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Target Activity | Välj i en lista över Target-aktiviteter eller dra och släpp en aktivitet från den vänstra listen.<br>**Obs!**Listan innehåller de senaste sex månaderna av aktiviteter som hade minst en träff. Om du inte ser någon aktivitet i listan kan den vara äldre än 6 månader. Den kan fortfarande läggas till från den vänstra listen, som har en summeringstid på upp till 18 månader. |
| Kontrollupplevelse | Välj din kontrollupplevelse. Du kan ändra den om det behövs i listrutan. |
| Normaliserar mätvärden | Välj bland unika besökare, besök eller aktivitetsexponeringar. Unika besökare rekommenderas för de flesta användningsfall för analyser. Detta mätvärde (även kallat beräkningsmetoden) blir nämnaren för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas. |
| Framgångsmått | Välj upp till tre standardhändelser (ej beräknade) från listrutorna, eller dra och släpp mätvärden från den vänstra listen. Varje mätvärde har en dedikerad tabell och visualisering på den renderade panelen. |
| Kalenderdatumintervall | Detta fylls i automatiskt baserat på aktivitetsdatumintervallet från Adobe Target. Du kan ändra den om det behövs. |

![Panel builder](assets/a4t-panel-builder.png)

## Panelutdata {#Output}

Panelen Analytics for Target returnerar en mängd data och visualiseringar som hjälper dig att bättre förstå hur din Adobe Target-aktivitet och dina upplevelser fungerar. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att klicka på redigeringspennan i det övre högra hörnet.

För varje framgångsmått du valt visas en frihandstabell och en konverteringsgrad:

![Återgiven](assets/a4t-rendered.png)


I varje frihandstabell visas följande måttkolumner:

| Mått | Beskrivning |
|---|---|
| Normaliserar mätvärden | Unika besökare, besök eller aktivitetsexponeringar. |
| Resultatmått | Det mått som valts i verktyget |
| Konverteringsgrad | Resultatmått/normaliseringsmått |
| Lyft | Jämför konverteringsgraden för varje upplevelse med kontrollupplevelsen.<br>**Obs!**Lyft är en&quot;låst mätmetod&quot; för Target upplevelser. den inte kan brytas ned eller användas med andra dimensioner. |
| Lyft (nedre) | Representerar den värsta klippet en variant kan ha över kontrollen. |
| Lyft (mitten) | Representerar mittpunktshöjningen som en variantupplevelse kan ha över kontrollen, med ett 95% konfidensintervall. Det här är&quot;Lyft&quot; i rapporter och Analytics. |
| Lyft (övre) | Representerar den bästa lyften en variantupplevelse kan ha över kontrollen. |
| Förtroende | Studenterna som ska testas beräknar konfidensnivån, vilket anger sannolikheten för att resultatet skulle dupliceras om testet kördes igen. Ett fast villkorsstyrt formateringsintervall på 75 %/85 %/95 % har tillämpats på måttet. Den här formateringen kan anpassas om det behövs under Kolumninställningar. <br>**Obs!**Förtroende är ett&quot;låst mått&quot; för Target upplevelser. den inte kan brytas ned eller användas med andra dimensioner. |

Precis som med andra paneler i Analysis Workspace kan du fortsätta att analysera genom att lägga till ytterligare tabeller och [visualiseringar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) som hjälper dig att analysera dina Adobe Target-aktiviteter.

## FAQs {#FAQ}

| Fråga | Svar |
|---|---|
| Vilka aktivitetstyper stöds i A4T? | [Läs mer](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) om vilka aktivitetstyper som stöds. |
| Stöds beräknade mätvärden vid lyftnings- och förtroendeberäkningar? | Nej. [Läs mer](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) om varför beräknade mätvärden inte stöds i lyft och självförtroende. Beräknade värden kan dock användas i A4T-rapporter utanför dessa mått. |
| Varför kan unika besökare variera mellan Target och Analytics? | [Läs mer](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) om olika unika besökare mellan produkter. |
| Varför returneras orelaterade upplevelser när jag väljer ett träffsegment för en viss Target-aktivitet i min analys? | A4T-dimensionen är en listvariabel, vilket betyder att den kan innehålla många aktiviteter (och upplevelser) samtidigt. [Läs mer](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| Betyder konfidensmätningen extrema order eller används en Bonferroni-korrigering för flera erbjudanden? | Nej. [Läs mer](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) om hur Analytics beräknar självförtroende. |

Mer information om Analytics för Target-rapportering finns på [A4T-rapportering](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
