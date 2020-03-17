---
title: Vanliga mätvärden på andra plattformar - översättningsguide
description: Lär dig hur du hämtar in mätdata för många vanliga rapporter med hjälp av terminologi som är mer bekant för Google Analytics-användare.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Vanliga mätvärden på andra plattformar - översättningsguide

På andra plattformar som Google Analytics har många rapporter ett gemensamt antal mätvärden. Använd den här sidan om du vill veta hur du återskapar mätvärden som används i många rapporter.

Om du vill lägga till flera mätvärden i en frihandstabell på arbetsytan drar du mätvärdena från komponentområdet bredvid måttrubriken på arbetsytan:

![Ytterligare mått](/help/technotes/ga-to-aa/assets/new_metric.png)

## Förvärvsstatistik

**Användare** är ungefär lika med **unika besökare** på arbetsytan. Mer information finns i måttet [Unika besökare](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) i användarhandboken för komponenter.

**Nya användare** kan hämtas på följande sätt:

1. Dra mätvärdena för **Unika besökare** till arbetsytan.
2. Dra **förstagångsbesökssegmentet** ovanför mätrubrikerna för unika besökare:

   ![Första gången du besöker](../assets/first_time_visits.png)

**Sessioner** är ungefär lika med **besök** i Analysis Workspace. Mer information finns i [Besök](/help/components/c-variables/c-metrics/metrics-visit.md) -måttet i användarhandboken för komponenter.

![Förvärvsstatistik](../assets/acquisition_metrics.png)

## Beteendemått

**Studsfrekvens** är lätt tillgängligt i Analysis Workspace som ett mått. Mer information finns i [Studsfrekvens](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) -måttet i användarhandboken för komponenter.

**Sidor/session** är ett beräknat mått. Den kan erhållas genom följande:

1. Om du redan har skapat det här beräknade måttet letar du reda på det under Metrisk och drar det till arbetsytan.
2. Om du ännu inte har skapat det beräknade måttet klickar du på **+** -ikonen bredvid mätningslistan för att öppna verktyget Beräknade mätvärden.
3. Ge den titeln &quot;Sidvisningar per besök&quot; och en beskrivning om så önskas.
4. Ställ in formatet till Decimal och ställ in antalet decimaler till 2.
5. Dra mätvärdena för **sidvyerna** och **besöken** till definitionsområdet.
6. Ordna definitionen så att formeln är **Sidvyer delat med Besök**.

   ![Sidvisningar per besök](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Klicka på Spara för att gå tillbaka till arbetsytan.
8. Dra det nydefinierade beräknade måttet till arbetsytan.

   Läs mer om [Beräknade mått](/help/components/c-variables/c-metrics/calculated-metric.md) i användarhandboken för komponenter.

**Medel. Sessionstiden** är ungefär lika med **tiden per besök (sekunder)**. Läs mer om [tidsåtgång](/help/components/c-variables/c-metrics/metrics-time-spent.md) i användarhandboken för komponenter.

## Konverteringsmått

**Målkonverteringsgrad**, **målslutföranden** och **målvärde** kräver ytterligare implementering på båda plattformarna. Om din implementering redan innehåller funktioner för produktdimensionen och inköpshändelsen ska du göra följande:

1. Dra mätvärdena för **Order** , **Revenue** och **Visits** till arbetsytan.
1. Skapa ett beräknat mått för **beställningar per besök**. Markera båda mätrubrikerna genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac) på båda mätrubrikerna. Högerklicka på någon av rubrikerna, välj **Skapa mätvärden från markering** och klicka sedan på **Dela**. Det nya måttet liknar en konverteringsgrad för mål.
1. Om du behöver använda decimaler redigerar du det beräknade måttet. Klicka på knappen Info i måtthuvudet och sedan på pennikonen. Lägg till 1 eller 2 decimaler i fönstret Beräknad metrisk byggare och klicka sedan på Spara.

   ![Beställningar per besök](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Om implementeringen ännu inte klarar produkt- eller konverteringsdata rekommenderar Adobe att man samarbetar med en implementeringskonsult för att säkerställa datakvalitet och -integritet.
