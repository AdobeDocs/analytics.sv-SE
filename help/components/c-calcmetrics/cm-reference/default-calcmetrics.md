---
description: Adobe tillhandahåller olika beräknade mätvärden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Standardberäknade värden
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: c132b21229aebea8121b156e1f4302a26b483ef5
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Standardberäknade värden

Adobe Analytics tillhandahåller olika beräknade värden som täcker de vanligaste användningsområdena. Dessa beräknade värden är tillgängliga som standard i Analysis Workspace.

Här följer en lista över alla beräknade mätvärden som tillhandahålls av Adobe, med dess avsedda funktion och den underliggande formel som används för att beräkna dem:

>[!NOTE]
>
>Förutom de standardvärden för beräknade värden som beskrivs på den här sidan kan du även lägga till ytterligare beräknade värden i en rapportserie.
>
>Ni kan:
>
> * Lägg till beräknade standardvärden för den direktuppspelade mediesamlingen, enligt beskrivningen i [Beräknade mått](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html?lang=sv-SE)
> * Skapa anpassade beräknade värden från befintliga mått, enligt beskrivningen i [Beräknade och avancerade beräknade värden](/help/components/c-calcmetrics/cm-overview.md).
>

>[!TIP]
>
>Använd [dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) för att mer ingående granska definitionen av ett beräknat standardmått och de enskilda komponenterna som utgör den definitionen.
>



| Namn på beräknat mätvärde | Funktion | Formel |
| --- | --- | --- |
| Länkklickningar för förvärv | Antalet gånger som personer klickar på en länk som är avsedd att köra trafik till platsen. | `[Campaign Click-throughs]` |
| Åtgärder | Det totala antalet åtgärder som har vidtagits i appen | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Appanvändare | Det totala antalet användare i en mobilapp | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Genomsnittlig sessionslängd (mobil) | Genomsnittlig tid som besökare tillbringar på webbplatsen under en enda session. | Tom |
| Genomsnittlig tid på plats | Genomsnittlig tid som en besökare tillbringar på webbplatsen innan han eller hon lämnar eller navigerar. | `[Average Time Spent on Site (Seconds)]` |
| Studsfrekvens | Andelen besök som innehöll exakt en träff jämfört med antalet besök på den sidan. Det här måttet kan hjälpa dig att förstå vilka dimensionsobjekt som har den högsta avhoppsfrekvensen eller att se en sammanlagd avhoppsfrekvens för din webbplats över tiden. | `[Bounces] / [Entries]` |
| Vyproportioner för startsida | Förhållandet mellan båda sidvyerna och det totala antalet sidvyer. | `[Bot Page Views] / [Page Views]` |
| Innehållshastighet | Hur snabbt nytt innehåll skapas och publiceras på webbplatsen och hur snabbt det genererar användarengagemang. | `[Page Views] / [Visits]` |
| Konverteringsgrad | Andelen besökare som vidtagit en önskad åtgärd, t.ex. gjort ett köp. | `[Orders] / [Visits]` |
| Ankomstfrekvens | Andelen besökare som kom in på webbplatsen på en viss sida, jämfört med det totala antalet sessioner på webbplatsen. | `[Entries] / [Visits]` |
| Beräknade unika besökare (ITP 2.1) | För ITP-besökare (användare i Safari-webbläsare), dividera unika besökare med 2 eller mindre. Detta beräknade mätresultat förutsätter att du anger cookies med JavaScript på klientsidan (inte med en CNAME-implementering). Implementeringar som ställer in cookies med JavaScript på klientsidan påverkades från och med ITP 2.1. Mer information finns i [Förebyggande av intelligent spårning](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID-täckning | Procentandel besökare som har ett Experience Cloud-ID. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Avsluta | Andelen besökare som lämnar webbplatsen efter att ha visat en viss sida. | `[Exits] / [Visits]` |
| ITP 2.1 Unika besökare/unika besökare | Andelen unika besökare som använder en webbläsare som påverkas av ITP 2.1-cookie-begränsningar. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Orderassistenter | Antalet gånger en kanal eller källa bidrog till kundens resa mot ett köp, men resulterade inte i det slutliga köpet. | `[Orders (Visit Participation)] - [Orders]` |
| Beställningar/besök | Procentandel besök på platsen som resulterar i en slutförd transaktion. | `[Orders] / [Visits]` |
| Beställningar/besökare | Genomsnittligt antal order eller transaktioner som genererats av varje enskild besökare på platsen | `[Orders] / [Unique Visitors]` |
| Sidvyer/beräknade unika besökare (ITP 2.1) | Genomsnittligt antal sidor som visas för beräknade unika besökare (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Sidvyer/unik besökare | Genomsnittligt antal sidor som visas för varje unik besökare på webbplatsen. | `[Page Views] / [Unique Visitors]` |
| Sidvyer/besök | Genomsnittligt antal sidor som en användare visar under ett enda besök på webbplatsen. | `[Page Views] / [Visits]` |
| Sidhastighet | Antalet ytterligare sidvyer som genereras av ett innehållsavsnitt. Detta kan hjälpa er att avgöra vilket innehåll som ökar engagemanget. | `[Page Views] / [Visits]` |
| Läs in igen/visa sidor | Procentandelen sidvyer som resulterade i en omladdning eller uppdatering av sidan. | `[Reloads] / [Page Views]` |
| Intäkter/order | Det genomsnittliga intäktsbelopp som genereras av varje slutförd transaktion eller order på webbplatsen. | `[Revenue] / [Orders]` |
| Intäkter/besök | Genomsnittlig intäkt som genererats av ett enda besök på webbplatsen. | `[Revenue] / [Visits]` |
| Intäkter/besökare | Det genomsnittliga intäktsbelopp som genereras av varje enskild besökare på webbplatsen. | `[Revenue] / [Unique Visitors]` |
| Lägesvy | Antalet vyer till olika lägen eller skärmar i appen | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Tid/användare (tillstånd) | Den tid som den genomsnittliga besökaren tillbringar i ett visst läge under tiden som han/hon befinner sig på webbplatsen | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Unika besökare/unika besökare som återvänder efter 7 dagar | Andelen unika besökare som återvänder efter en period på 7 dagar eller mer. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Användare (mobil) | Det totala antalet användare i en mobilapp | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Besök/besökare | Genomsnittligt antal besök som en unik besökare gör på webbplatsen. | `[Visits] / [Unique Visitors]` |
| Viktad studs-hastighet | Funktion | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
