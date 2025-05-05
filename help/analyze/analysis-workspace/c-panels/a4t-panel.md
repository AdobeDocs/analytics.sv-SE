---
description: Med Analytics for Target-panelen (A4T) kan du analysera dina Adobe Target-aktiviteter och -upplevelser i Analysis Workspace.
title: Analyser för målpanelen (A4T)
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 0%

---

# Analyser för målpanelen {#analyze-for-target-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_button"
>title="Analyser för Target"
>abstract="Analysera Target-aktiviteter och -upplevelser i Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_panel"
>title="Analyser för målpanelen"
>abstract="Analysera Target-aktiviteter och -upplevelser i Analysis Workspace.<br/><br>**Parametrar &#x200B;**<br/>**Målaktivitet**: Målaktiviteten som analyseras.<br/>**Kontrollupplevelse**: Kontrollupplevelse för den valda målaktiviteten.<br/>**Normaliserar mätvärden**: Besökare, besök eller visningar. Detta mätvärde (även kallat beräkningsmetoden) blir nämnaren för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas.<br/>**Framgångsmått**: Upp till tre standardvärden (ej beräknade) för lyckade resultat som målaktiviteten ska analyseras mot."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Den här artikeln dokumenterar panelen Analytics for Target i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_På [Experimentationspanelen](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) finns information om hur du jämför olika användarupplevelser, marknadsförings- och meddelandevariationer i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Med Analytics for Target-panelen kan ni analysera era Adobe Target-aktiviteter och -upplevelser i Analysis Workspace. Panelen ger dig också möjlighet att se hur du kan höja din kreativitet och ditt förtroende för upp till tre framgångsmått. Navigera till en rapportsvit med Analytics for Target-komponenter aktiverade för att komma åt Analytics för Target-panelen. Välj sedan panelikonen längst till vänster och dra Analytics for Target-panelen till ditt Analysis Workspace-projekt.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analytics for Target panel](https://video.tv.adobe.com/v/37247?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

## Använd

Så här använder du en **[!UICONTROL Analytics for Target]**-panel:

1. Skapa en **[!UICONTROL Analytics for Target]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata {#panel-nput}

Du kan konfigurera Analytics för målpanelen med följande indatainställningar:

![Indata från A4T-panelen](assets/a4t-panel-input.png)

| Inställning | Beskrivning |
|---|---|
| **[!UICONTROL Target Activity]** | Välj i en lista över målaktiviteter. Listan innehåller de senaste sex månaderna av aktiviteter som hade minst en träff. Om ingen aktivitet visas i listan kan den vara äldre än 6 månader. Den kan fortfarande läggas till från den vänstra listen, som har en summeringstid på upp till 18 månader. |
| **[!UICONTROL Control Experience]** | Välj kontrollupplevelse. |
| **[!UICONTROL Normalizing metric]** | Välj Besökare, Besök eller Impressions. [!UICONTROL Visitors] rekommenderas för de flesta användningsfall för analys. Detta mätvärde (även kallat beräkningsmetoden) blir nämnaren för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas. |
| **[!UICONTROL Success metrics]** | Välj upp till tre standardhändelser (ej beräknade) i listrutan eller dra och släpp mätvärden från Metrics (Mätvärden) i komponentfältet. Varje mätvärde har en dedikerad tabell och visualisering på den renderade panelen. |

Välj **[!UICONTROL Build]** om du vill skapa panelen.

### Panelutdata {#panel-output}

Analytics for Target-panelen returnerar en mängd data och visualiseringar som hjälper er att bättre förstå hur Adobe Target aktiviteter och upplevelser fungerar. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. För varje framgångsmått som du har valt visas en [friformstabell](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) och en [Line](/help/analyze/analysis-workspace/visualizations/line.md)-visualisering som visar trenden för konverteringsgrad:

![Återgiven](assets/a4t-panel-output.png)

I varje frihandstabell visas följande måttkolumner:

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Normalizing metrics]** | Det normaliseringsmått som valts i indatapanelen: Unika besökare, besök eller aktivitetsimpressioner. |
| **[!UICONTROL Success metric]** | Det framgångsmått som valts på indatapanelen. |
| **[!UICONTROL Conversion rate]** | Mätvärdet för lyckad/normalisering. |
| **[!UICONTROL Lift]** | Jämför konverteringsgraden för varje upplevelse med kontrollupplevelsen. Obs! Lyft är ett *låst mätvärde* för målupplevelser. Det kan inte delas upp eller användas med andra dimensioner. |
| **[!UICONTROL Lift (Lower)]** | Detta värde är det värsta klippet en variantupplevelse kan ha över kontrollen, med ett 95% konfidensintervall.<br>Mer information finns i [Statistiska beräkningar](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) och Excel-filen [Slutför konfidensberäkning](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx). |
| **[!UICONTROL Lift (Mid)]** | Detta värde representerar den mittpunktshöjning en variantupplevelse kan ha över kontrollen, med ett 95% konfidensintervall. <br>Mer information finns i [Statistiska beräkningar](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) och Excel-filen [Slutför konfidensberäkning](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx). |
| **[!UICONTROL Lift (Upper)]** | Detta värde representerar den bästa lyften en variantupplevelse kan ha över kontrollen, med ett 95% konfidensintervall.<br>Mer information finns i [Statistiska beräkningar](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) och Excel-filen [Slutför konfidensberäkning](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx). |
| **[!UICONTROL Confidence]** | Studenterna som ska testas beräknar konfidensnivån, vilket anger sannolikheten för att resultatet skulle dupliceras om testet kördes igen. Ett fast villkorsstyrt formateringsintervall på 75 %/85 %/95 % har tillämpats på måttet. Den här formateringen kan anpassas om det behövs under Kolumninställningar. Obs! Konfidensen är ett låst mått för Target Experiences. Det kan inte delas upp eller användas med andra dimensioner.<br>Mer information finns i [Statistiska beräkningar](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) och Excel-filen [Slutför konfidensberäkning](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx). |

Precis som med andra paneler i Analysis Workspace kan du fortsätta att analysera genom att lägga till ytterligare tabeller och [visualiseringar](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations) som hjälper dig att analysera dina Adobe Target-aktiviteter. Du kan också använda ett segment på panelnivå eller i frihandstabellen. Observera, att om du lägger till den i frihandstabellen måste du täcka över hela tabellen för att lyftnings- och förtroendeberäkningarna ska bevaras. För närvarande stöds inte kolumnnivåsegment.

Använd ![Redigera](/help/assets/icons/Edit.svg) för att konfigurera om och återskapa panelen.

## Vanliga frågor {#FAQ}

| Fråga | Svar |
|---|---|
| Vilka aktivitetstyper stöds i Analytics for Target? | [Läs mer](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup) om vilka aktivitetstyper som stöds. |
| Stöds beräknade mätvärden vid lyftnings- och förtroendeberäkningar? | Nej. [Läs mer](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) om varför beräknade värden inte stöds i lyft och självförtroende. Beräknade mätvärden kan dock användas i Analytics för Target-rapportering utanför dessa mätvärden. |
| Varför varierar unika besökare mellan Target och Analytics? | [Läs mer](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) om varianterna mellan unika besökare. |
| När jag använder ett träffsegment för en viss Target-aktivitet i min analys, varför ser jag då orelaterade upplevelser returneras? | Analytics för Target-dimensionen är en listvariabel, vilket innebär att den kan innehålla många aktiviteter (och upplevelser) samtidigt. [Läs mer](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) |
| Betyder konfidensmätningen extrema order eller används en Bonferroni-korrigering för flera erbjudanden? | Nej. [Läs mer](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) om hur Analytics beräknar förtroendet. |
| Kan lyftnings- och tillförlitlighetsvärden användas med andra dimensioner eller uppdelningar? | Lyft och självförtroende är&quot;låsta mätvärden&quot; för Target Experiences-dimensionen eftersom de kräver en kontroll och variant som kan beräknas över. De kan därför inte delas upp eller användas med andra dimensioner. |
| När beräknas lyft och självförtroende om? | Lyft och beräkna tryggheten igen när panelen byggs, när panelens datumintervall ändras eller när ett segment tillämpas på panelen eller tabellen. När du tillämpar ett segmentfilter på frihandstabellen måste segmentet appliceras på alla kolumner, annars uppdateras inte hissen och förtroendet inte korrekt. Segment på kolumnnivå stöds inte. |

Mer information om Analytics för Target-rapportering finns på [Analytics for Target Reporting](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/reporting)
