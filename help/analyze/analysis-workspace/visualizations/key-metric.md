---
description: Använd den centrala metriska sammanfattningen för att jämföra mätprestanda för två tidslinjer.
title: Sammanfattning av nyckelmått
feature: Visualizations
role: User, Admin
source-git-commit: a126f51c82cf7b23f4e03134c2d870d216dadc47
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---


# Sammanfattning av nyckelmått

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

Med hjälp av nyckelmätningssammanfattningen kan du se hur ett viktigt mätresultat trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. Det ger fördelarna med flera visualiseringar i kombination med en visualisering:

* **[!UICONTROL Line]** visualiseringar som visar hur måttet trendar för det primära datumintervallet och jämförelsedatumintervallet

* **[!UICONTROL Summary percent change]** som visar måttökning eller minskning mellan det primära datumintervallet och jämförelsedatumintervallet

* Aktuellt totalvärde ([!UICONTROL **samlingsnummer**]) för måttet

## Användningsexempel

Den här visualiseringen åtgärdar ett antal vanliga användningsområden, bland annat:

* En analytiker som försöker förstå hur skapandet av nya affärsmöjligheter såg ut den här månaden jämfört med samma tidsram förra året.

* En marknadsförare som visar hur leadgenerering för en viss lead-typ har ändrats från den här månaden till den förra månaden.

* En chef vill förstå hur nya bokningar ändrades från detta kvartal till förra kvartalet.

## Konfigurera sammanfattningen av nyckelmått

1. Dra **[!UICONTROL Key metric summary]** visualisering från **[!UICONTROL Visualizations]** menyn i den vänstra listen i en panel.

1. Konfigurera visualiseringen genom att välja ett mätvärde, ett primärt datumintervall och ett jämförelsedatumintervall och ett segment (om det behövs):

   ![](assets/key-metric-config.png)

   | Konfigurationsinställning | Definition |
   | --- | --- |
   | **[!UICONTROL Metric]** | Välj det mätvärde som du vill undersöka. Alla mätvärden stöds. |
   | **[!UICONTROL Primary date range]** | Det aktuella datumintervallet för frihandstabellen. |
   | **[!UICONTROL Comparison date range]** | Datumintervallet som du vill jämföra det primära datumintervallet med. |
   | **[!UICONTROL Segment (optional)]** | Alla segment som du är intresserad av för den här sammanfattningen. |

   {style=&quot;table-layout:auto&quot;}

1. Klicka på **[!UICONTROL Build]**.

## Visa utdata

![](assets/key-metric-output.png)

Observera:

* The **[!UICONTROL Previous period]** linjediagram (alltid grått) motsvarar **[!UICONTROL Comparison date range]** i konfigurationssteget.

* Om ett datumintervall för jämförelse inte väljs under konfigurationen eller döljs i visualiseringsinställningarna (mer i inställningarna nedan) visas bara linjediagrammet för det primära datumintervallet. Sammanfattningsändringen döljs.

* Härifrån kan du hovra över linjediagrammen för att se statistik för enskilda dagar:

![](assets/key-metric-output2.png)

## Visualiseringsinställningar

Sammanfattningen av nyckeltal erbjuder flera flexibla inställningar för bättre rapportering och kommunikation av viktiga mätvärden. Du kommer åt inställningarna via kugghjulsikonen i det övre högra hörnet av visualiseringen.

![](assets/key-metric-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| Betonar procentuell ändring | Visa sammanfattningsändring i framträdande fetstil i mitten av visualiseringen |
| Betonar talvärde | Visa sammanfattningsnummer i framträdande fetstil i mitten av visualiseringen |
| Förklaring synlig | Visa eller dölj teckenförklaringen längst ned i visualiseringen |
| Visa anteckningar | Visa eller dölj anteckningar som lagts till av en administratör |
| Visa miniatyrbilder | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt |
| Visa min och max i miniatyrdiagram | Visa eller dölj lägsta och högsta värden i primära och jämförande raddiagram |
| Visa jämförelse | Visa eller dölj jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
| Visa totalt nummer | Visa eller dölj sammanfattningsnummer |
| Visa rådifferens | Visa eller dölj den obearbetade skillnaden mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet |
| Förkortningsvärde | Förkorta talvärdena för att förenkla kommunikationen (t.ex. 20 000 -> 20 kB) |

## Redigera visualisering

När du har skapat visualiseringen kan du fortfarande redigera den ursprungliga konfigurationen.

1. Klicka på pennikonen i det övre högra hörnet av visualiseringen (bredvid inställningsikonen).

   ![](assets/edit-icon.png)

   Du återgår nu till den ursprungliga konfigurationsvyn.

1. Ändra måttet, det primära datumintervallet, jämförelsedatumintervallet eller segmentet.
