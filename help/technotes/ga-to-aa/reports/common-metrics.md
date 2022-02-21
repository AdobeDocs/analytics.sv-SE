---
title: Vanliga mätvärden på andra plattformar - översättningsguide
description: Lär dig hur du hämtar in mätdata för många vanliga rapporter med hjälp av terminologi som är mer välbekant för Google Analytics-användare.
feature: Third-party Integration
exl-id: e95b0530-8099-4a08-9e2b-75174546277d
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Vanliga mätvärden på andra plattformar - översättningsguide

På andra plattformar som Google Analytics har många rapporter ett gemensamt antal mätvärden. Använd den här sidan om du vill veta hur du återskapar mätvärden som används i många rapporter.

Om du vill lägga till flera mätvärden i en frihandstabell på arbetsytan drar du mätvärdena från komponentområdet bredvid måttrubriken på arbetsytan:

![Ytterligare mått](/help/technotes/ga-to-aa/assets/new_metric.png)

## Förvärvsstatistik

**Användare** är ungefär lika med **Unika besökare** i Workspace. Se [Unika besökare](/help/components/metrics/unique-visitors.md) i användarhandboken för komponenter finns mer information.

**Nya användare** kan erhållas genom följande:

1. Dra **Unika besökare** mätvärden på arbetsytan.
2. Dra **Första gången du besöker** segment ovanför måttrubrikerna för unika besökare:

   ![Första gången du besöker](../assets/first_time_visits.png)

**Sessioner** är ungefär lika med **Besök** i Analysis Workspace. Se [Besök](/help/components/metrics/visits.md) i användarhandboken för komponenter finns mer information.

![Förvärvsstatistik](../assets/acquisition_metrics.png)

## Beteendemått

**Studsfrekvens** finns i Analysis Workspace som mätvärden. Se [Studsfrekvens](/help/components/metrics/bounce-rate.md) i användarhandboken för komponenter finns mer information.

**Sidor/session** är ett beräknat mått. Den kan erhållas genom följande:

1. Om du redan har skapat det här beräknade måttet letar du reda på det under Metrisk och drar det till arbetsytan.
2. Om du ännu inte har skapat det beräknade måttet klickar du på **+** -ikonen nära måttlistan för att öppna beräkningsverktyget.
3. Ge den titeln &quot;Sidvisningar per besök&quot; och en beskrivning om så önskas.
4. Ställ in formatet till Decimal och ställ in antalet decimaler till 2.
5. Dra **Sidvyer** mätvärden och **Besök** i definitionsområdet.
6. Ordna definitionen så att formeln **Sidvyer delade med besök**.

   ![Sidvisningar per besök](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. Klicka på Spara för att gå tillbaka till arbetsytan.
8. Dra det nydefinierade beräknade måttet till arbetsytan.

   Läs mer om [Beräknade mått](/help/components/c-calcmetrics/cm-overview.md) i användarhandboken för komponenter.

**Medel Sessionsvaraktighet** är ungefär lika med **Tid per besök (sekunder)**. Läs mer om [Tid per besök](/help/components/metrics/time-spent-per-visit.md) mått i användarhandboken för komponenter.

## Konverteringsmått

**Målkonverteringsgrad**, **Måluppfyllelse** och **Målvärde** kräver ytterligare implementering på båda plattformarna. Om din implementering redan innehåller funktioner för produktdimensionen och inköpshändelsen ska du göra följande:

1. Dra **Beställningar** Mätvärden. **Intäkter** och **Besök** mätvärden på arbetsytan.
1. Skapa ett beräknat mått på **Beställningar per besök**. Markera båda mätrubrikerna genom att Ctrl-klicka (Windows) eller Kommando-klicka (Mac). Högerklicka på någon av rubrikerna och välj **Skapa mått från markering** och sedan klicka **Dela**. Det nya måttet liknar en konverteringsgrad för mål.
1. Om du behöver använda decimaler redigerar du det beräknade måttet. Klicka på knappen Info i måtthuvudet och sedan på pennikonen. Lägg till 1 eller 2 decimaler i fönstret Beräknad metrisk byggare och klicka sedan på Spara.

   ![Beställningar per besök](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

Om implementeringen ännu inte klarar produkt- eller konverteringsdata rekommenderar Adobe att man samarbetar med en implementeringskonsult för att säkerställa datakvalitet och dataintegritet.
