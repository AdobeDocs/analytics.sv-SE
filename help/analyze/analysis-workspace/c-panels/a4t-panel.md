---
description: Med Analytics for Target-panelen (A4T) kan ni analysera era Adobe Target-aktiviteter och -upplevelser i Analysis Workspace.
title: Analyser för målpanelen (A4T)
translation-type: tm+mt
source-git-commit: 354bc118c869bd926a1cef0a75f5133d1a410cd5
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---


# Analyser för målpanelen (A4T)

>[!IMPORTANT]
>
>**[!UICONTROL Analytics for Target (A4T)]** Panelen har för närvarande begränsad testning. [Läs mer](https://docs.adobe.com/content/help/en/analytics/landing/an-releases.html)

På A4T-panelen (Analytics for Target) kan du analysera dina Adobe Target-aktiviteter och -upplevelser i Analysis Workspace. Det gör det också möjligt för er att se hur ni lyfter och litar på upp till tre framgångsvärden. Om du vill komma åt A4T-panelen går du till en rapportsvit där A4T-komponenter är aktiverade. Klicka sedan på panelikonen längst till vänster och dra Analytics for Target-panelen till Analysis Workspace Project.

## Panel Builder

Du kan konfigurera A4T-panelen med följande inställningar:

| Inställning | Beskrivning |
|---|---|
| Verksamhetens syfte? | Välj i en lista över målaktiviteter eller dra och släpp en aktivitet från den vänstra listen.<br>**Obs!**Listan innehåller de senaste sex månaderna av aktiviteter som hade minst en träff. Om du inte ser någon aktivitet i listan kan den vara äldre än 6 månader. Den kan fortfarande läggas till från den vänstra listen, som har en summeringstid på upp till 18 månader. |
| Kontrollupplevelse | Välj din kontrollupplevelse. Du kan ändra den om det behövs i listrutan. |
| Normaliserar mätvärden | Välj bland unika besökare, besök eller aktivitetsexponeringar. Unika besökare rekommenderas för de flesta användningsfall för analyser. |
| Framgångsmått | Välj upp till tre standardhändelser i listrutorna eller dra och släpp mätvärden från den vänstra listen. Varje mätvärde har en dedikerad tabell och visualisering på den renderade panelen. |
| Kalenderdatumintervall | Detta fylls i automatiskt baserat på aktivitetsdatumintervallet från Adobe Target. Du kan ändra den om det behövs. |

![](assets/a4t-panel-builder.png)

## Panelutdata

Analytics for Target-panelen returnerar en mängd data och visualiseringar som hjälper er att bättre förstå hur er Adobe Target-aktivitet och -upplevelser fungerar. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att klicka på redigeringspennan i det övre högra hörnet.

För varje framgångsmått du valt visas en frihandstabell och en konverteringsgrad:

![](assets/a4t-rendered.png)

I varje frihandstabell visas följande måttkolumner:

| Mått | Beskrivning |
|---|---|
| Normaliserar mätvärden | Unika besökare, besök eller aktivitetsexponeringar. |
| Resultatmått | Det mått som valts i verktyget |
| Konverteringsgrad | Resultatmått/normaliseringsmått |
| Lyft | Jämför konverteringsgraden för varje upplevelse med kontrollupplevelsen.<br>**Obs!**Lyft är ett&quot;låst mätvärde&quot; för Target-upplevelser. den inte kan brytas ned eller användas med andra dimensioner. |
| Lyft (nedre) | Representerar den värsta klippet en variant kan ha över kontrollen. |
| Lyft (mitten) | Representerar mittpunktshöjningen som en variantupplevelse kan ha över kontrollen, med ett 95% konfidensintervall. Det här är&quot;Lyft&quot; i rapporter och analyser. |
| Lyft (övre) | Representerar den bästa lyften en variantupplevelse kan ha över kontrollen. |
| Förtroende | Studenterna som ska testas beräknar konfidensnivån, vilket anger sannolikheten för att resultatet skulle dupliceras om testet kördes igen. Ett fast villkorsstyrt formateringsintervall på 75 %/85 %/95 % har tillämpats på måttet. Den här formateringen kan anpassas om det behövs under Kolumninställningar. <br>**Obs!**Förtroende är ett&quot;låst mått&quot; för upplevelser i Adobe Target. Den kan inte delas upp eller användas med andra dimensioner. |

Precis som med andra paneler i Analysis Workspace kan du fortsätta att analysera genom att lägga till ytterligare tabeller och [visualiseringar](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) som hjälper dig att analysera dina Adobe Target-aktiviteter.

Mer information om Analytics för Target-rapportering finns på [A4T-rapportering](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
