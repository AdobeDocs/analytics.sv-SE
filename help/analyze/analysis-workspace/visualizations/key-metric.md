---
description: Använd den centrala metriska sammanfattningen för att jämföra mätprestanda för två tidslinjer.
title: Sammanfattning av nyckelmått
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 0%

---

# Sammanfattning av nyckelmått {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Sammanfattning av nyckelmått"
>abstract="Skapa en visualisering som är en kombination av rad-, sammanfattningsändrings- och sammanfattningsnummerdiagram. Använd den här visualiseringen för att jämföra hur viktiga mätvärden är trender mellan två tidsperioder."


>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras visualiseringen av nyckelmätvärden i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Se [Sammanfattning av nyckeltal](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


Med visualiseringen ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** kan du se hur ett viktigt mätresultat trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. Det ger fördelarna med flera visualiseringar i kombination med en visualisering:

* **[!UICONTROL Line]**-visualisering visar hur måttet trendar för det primära datumintervallet och jämförelsedatumintervallet

* **[!UICONTROL Summary percent change]** visar ökning eller minskning av måttet mellan det primära datumintervallet och jämförelsedatumintervallet

* Aktuellt totalt värde ([!UICONTROL **sammanfattningsnummer**]) för måttet

## Användningsexempel

Den här visualiseringen åtgärdar flera vanliga användningsfall, bland annat:

* En analytiker som försöker förstå hur skapandet av nya affärsmöjligheter såg ut den här månaden jämfört med samma tidsram förra året.

* En marknadsförare som visar hur leadgenerering för en viss lead-typ har ändrats från den här månaden till den förra månaden.

* En chefer vill förstå hur nya bokningar ändrades från detta kvartal till förra kvartalet.

## Använd

1. Lägg till en ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]**-visualisering. Se [Lägga till en visualisering på en panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Konfigurera visualiseringen genom att välja **[!UICONTROL Metric]**, **[!UICONTROL Primary date range]**, **[!UICONTROL Comparison date range]** (valfritt) och **[!UICONTROL Filter]** (valfritt):

   ![Nyckelmätningskonfiguration som visar alternativen för mått, primärt datumintervall, jämförelsedatumintervall och segment.](assets/key-metrics-config.png)

   | Alternativ | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Metric]** | Välj det mätvärde som du vill undersöka. Alla mätvärden stöds. |
   | **[!UICONTROL Primary date range]** | Det aktuella datumintervallet för frihandstabellen.<p>Välj bland tillgängliga datumintervall i datavyn.</p> <p>Välj [!UICONTROL **Panelens datumintervall**] om du vill använda samma datumintervall som används på panelen där visualiseringen finns.</p> |
   | **[!UICONTROL Comparison date range]** | Datumintervallet som du vill jämföra med det primära datumintervallet. |
   | **[!UICONTROL Segment (optional)]** | Alla segment som du är intresserad av för sammanfattningen. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >När fältet [!UICONTROL **Primärt datumintervall**] är inställt på [!UICONTROL **Paneldatumintervall**] kan **[!UICONTROL Comparison date range]** uppdateras automatiskt, beroende på om alternativet **[!UICONTROL Comparison date range]** är relativt till det primära datumintervallet eller fasta.
   >
   >* **Relativ:** Om fältet **[!UICONTROL Comparison date range]** är inställt på ett alternativ som är relativt till det primära datumintervallet (t.ex. [!UICONTROL **Föregående dag**], [!UICONTROL **Samma dag förra veckan**], [!UICONTROL **Samma dag fyra veckor före**] o.s.v.) kommer eventuella uppdateringar av fältet [!UICONTROL **Primärt datumintervall**] automatiskt att uppdatera till perioden som omedelbart kommer efter panelens datumintervall.**[!UICONTROL Comparison date range]**
   >* **Fast:** Om fältet [!UICONTROL **Jämförelsedatumintervall**] är inställt på ett fast datumintervall (t.ex. **3 februari 2023**) har ändringar som gjorts i fältet [!UICONTROL **Primärt datumintervall**] eller panelens datumintervall ingen effekt på [!UICONTROL **Jämförelsedatumintervallet**]. Alla uppdateringar av panelens datumintervall gör dock att [!UICONTROL **primärt datumintervall**] uppdateras automatiskt.

1. Välj **[!UICONTROL Build]**.

Resultatet av sammanfattningen av nyckeltal ser ut så här:

![Viktiga måttutdata som visar metik-, sammanfattningsändring-, sammanfattningsnummer- och linjediagram.](assets/key-metrics.png)

Tänk på följande när du visar utdata:

* Linjediagrammet **[!UICONTROL Previous period]** (visas alltid i grått) motsvarar **[!UICONTROL Comparison date range]** i konfigurationssteget.

* Om ett jämförelsedatumintervall inte anges under konfigurationen eller döljs i visualiseringsinställningarna, visas bara linjediagrammet för det primära datumintervallet. Sammanfattningsändringen är dold.

* Härifrån kan du hovra över linjediagrammen för att se statistik för enskilda dagar:


## Konfigurera

När du har skapat visualiseringen kan du redigera den ursprungliga konfigurationen.

1. Välj ![Redigera](/help/assets/icons/Edit.svg) **[!UICONTROL Configure visualization]** högst upp i visualiseringen.

   Du dirigeras tillbaka till den ursprungliga konfigurationsdialogrutan.

1. Ändra inställningarna. Välj **[!UICONTROL Reset]** om du vill återställa de aktuella inställningarna. Välj **[!UICONTROL Build]** om du vill återskapa visualiseringen.

## Inställningar

Som en del av visualiseringsinställningarna finns det specifika viktiga sammanfattningsinställningar.

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visa sammanfattningsändring i framträdande fetstil i mitten av visualiseringen |
| **[!UICONTROL Emphasize number value]** | Visa sammanfattningsnummer i framträdande fetstil i mitten av visualiseringen |
| **[!UICONTROL Legend visible]** | Visa eller dölj teckenförklaringen längst ned i visualiseringen |
| **[!UICONTROL Show annotations]** | Visa eller dölj anteckningar som lagts till av en administratör |
| **[!UICONTROL Hide title]** | Dölj visualiseringens titel. |
| **[!UICONTROL Percentages]** | Visar visualiseringen i procent i stället för ett tal. |
| **[!UICONTROL Show trendlines]** | Visa trendlinjer i visualiseringen. |
| **[!UICONTROL Show max and min on trendlines]** | Visa eller dölj lägsta och högsta värden i primära och jämförande raddiagram |
| **[!UICONTROL Show comparison percentage and trendline]** | Visa eller dölj jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
| **[!UICONTROL Show total number]** | Visa eller dölj sammanfattningsnummer |
| **[!UICONTROL Show raw difference]** | Visa eller dölj den obearbetade skillnaden mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet |
| **[!UICONTROL Abbreviate value]** | Välj **[!UICONTROL Abbreviate value]** om du vill förkorta talvärdet på ett intelligent sätt. När du har markerat det här alternativet anger du ett tal för att definiera förkortningen. Till exempel:<br/><table><tr><td>**Ursprungligt värde**</td><td>**Förkortning**</td><td>**Resultat**</td></tr><tr><td>12 011 141,25 USD</td><td>Inte markerad</td><td align="right">12 011 141,25 USD</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på 1</td><td align="right">12 miljoner dollar</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på 2</td><td align="right">$12.0M</td></tr><tr><td>12 011 141,25 USD</td><td>Markerad, inställd på 2</td><td align="right">$12.011M</td></tr><tr><td>12 011 141,25 USD</td><td>Markera, ange till 3</td><td align="right">$12.011M</td></tr></table> |

## Redigera visualisering

När du har skapat visualiseringen kan du redigera den ursprungliga konfigurationen.

1. Välj ![Redigera](/help/assets/icons/Edit.svg) i det övre högra hörnet av visualiseringen.


   Du dirigeras nu tillbaka till den ursprungliga [konfigurationsvyn](#configure).

1. Ändra måttet, det primära datumintervallet, jämförelsedatumintervallet eller segmentet.

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Visualiseringsinställningar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Snabbmenyn Visualisering ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

