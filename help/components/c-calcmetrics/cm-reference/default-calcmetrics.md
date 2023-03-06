---
description: Adobe tillhandahåller olika beräknade värden som du kan använda. På den här sidan visas dessa mått och deras avsedda användning.
title: Referensfunktioner
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 2874ea66765e650a92bc39537d6a9eb8cebcd6a4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 6%

---

# Standardberäknade värden

Adobe Analytics tillhandahåller olika beräknade värden som täcker de vanligaste användningsområdena. Dessa beräknade värden är som standard tillgängliga i Analysis Workspace.

Här följer en lista över alla beräknade mätvärden som tillhandahålls av Adobe, med dess avsedda funktion och den underliggande formel som används för att beräkna dem:

>[!NOTE]
>
>Förutom de beräknade standardvärden som beskrivs på den här sidan kan du även lägga till ytterligare beräknade värden i en rapportserie.
>
>Ni kan:
> * Lägg till beräknade standardvärden för direktuppspelningsmedia enligt beskrivningen i [Beräknade mått](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Skapa anpassade beräknade värden från befintliga mått, enligt beskrivningen i [Beräknade och avancerade beräknade (härledda) värden](/help/components/c-calcmetrics/cm-overview.md).



| Namn på beräknat mått |  -funktion | Formel |
|---------|----------|---------|
| Studsfrekvens | Andelen besök som innehöll exakt en träff jämfört med antalet besök på den sidan. Detta kan hjälpa dig att förstå vilka dimensionsobjekt som har den högsta studsfrekvensen eller att se en sammanlagd totalstuds för din webbplats över tiden. | Studsfrekvens |
| Intäkter/besökare | Det genomsnittliga intäktsbelopp som genereras av varje enskild besökare på webbplatsen. | <p>Intäkter</p><p>/</p><p>Unika besökare</p> |
| Beställningar/besökare | Genomsnittligt antal order eller transaktioner som genererats av varje enskild besökare på platsen | <p>Standardorder</p><p>/</p><p>Besökare</p> |
| Intäkter/besök | Den genomsnittliga intäkten från ett enda besök på webbplatsen. | <p>Intäkter</p><p>/</p><p>Unika besök</p> |
| Intäkter/order | Det genomsnittliga intäktsbelopp som genereras av varje slutförd transaktion eller order på webbplatsen. | <p>Intäkter</p><p>/</p><p>Order</p> |
| Beställningar/besök | Procentandel besök på platsen som resulterar i en slutförd transaktion. | <p>Order</p><p>/</p><p>Besök</p> |
| Sidvyer/besök | Genomsnittligt antal sidor som en användare visar under ett enda besök på webbplatsen. | <p>Sidvisningar</p><p>/</p><p>Besök</p> |
| Besök/besökare | Genomsnittligt antal besök som en unik besökare gör på webbplatsen. | <p>Besök</p><p>/</p><p>Unika besökare</p> |
| Läser in igen/Sidor | Procentandelen sidvyer som resulterade i en omladdning eller uppdatering av sidan. | <p>Siduppdateringar</p><p>/</p><p>Sidvisningar</p> |
| Viktad studs-hastighet |  -funktion | if(visit>percentile(visit),bouncerate,0) |
| Orderassistenter | Antalet gånger en kanal eller källa bidrog till kundens resa mot ett köp, men resulterade inte i det slutliga köpet. | <p>Beställningar (deltagande\|Besök)</p><p>-</p><p>Beställningar</p> |
| Utgångshastighet | Andelen besökare som lämnar webbplatsen efter att ha visat en viss sida. | <p>Sista besökssida</p><p>/</p><p>Besök</p> |
| Ankomstfrekvens | Andelen besökare som kom in på webbplatsen på en viss sida, jämfört med det totala antalet sessioner på webbplatsen. | <p>Första besökssida</p><p>/</p><p>Besök</p> |
| Genomsnittlig tid på plats | Den genomsnittliga tid en besökare tillbringar på webbplatsen innan han/hon lämnar eller navigerar. | Genomsnittlig tid spenderad på plats (sekunder) |
| Tid/användare (tillstånd) | Den tid som den genomsnittliga besökaren tillbringar i ett visst läge under tiden som han/hon befinner sig på webbplatsen | Tidsåtgång per besökare (sekunder), mått + mobilappssegment |
| Användare (mobil) | Det totala antalet användare i en mobilapp | Unika besökarmått + segmentet Användare av mobilappar |
| Appanvändare | Det totala antalet användare i en mobilapp | Unika besökarmått + mobilappssegment |
| Lägesvyer | Antalet vyer till olika lägen eller skärmar i appen | Mått för sidvisning + mobilappssegment |
| Åtgärder | Det totala antalet åtgärder som har vidtagits i appen | Mått för anpassade länkinstanser + Har ett åtgärdssegment |
| Länkklickningar för förvärv | Antalet gånger som personer klickar på en länk som är avsedd att köra trafik till platsen. | Mätvärden för kampanjklickningar |
| Sidhastighet | Antalet ytterligare sidvyer som genereras av ett innehållsavsnitt. Detta kan hjälpa er att avgöra vilket innehåll som ökar engagemanget. | <p>Sidvisningar</p><p>/</p><p>Besök</p> |
| Konverteringsgrad | Andelen besökare som vidtagit en önskad åtgärd, till exempel gjort ett köp. | <p>Beställningar</p><p>/</p><p>Besök</p> |
| Genomsnittlig sessionslängd (mobil) | Genomsnittlig tid som besökare tillbringar på webbplatsen under en enda session. | Tom |
| Experience Cloud ID-täckning | Andelen besökare som har ett Experience Cloud-ID. | <p>Besökare med Experience Cloud ID</p><p>/</p><p>Unika besökare</p> |
| Innehållshastighet | Hur snabbt nytt innehåll skapas och publiceras på webbplatsen och hur snabbt det genererar användarengagemang. | <p>Sidvisningar</p><p>/</p><p>Besök</p> |
| ITP 2.1 Unika besökare/unika besökare | Andelen unika besökare som använder en webbläsare som påverkas av ITP 2.1-cookie-begränsningar. Kunder som inte använder en CNAME-implementering. (Detta gäller kunder som ställer in cookies via JavaScript på klientsidan.) | <p>Unika besökarmått + segmentet ITP-besökare</p><p>/</p><p>Unika besökare</p> |
| Unika besökare/unika besökare som återvänder efter 7 dagar | Andelen unika besökare som återvänder efter en period på 7 dagar eller mer. | <p>Unik besökarstatistik + Användare returnerar efter 7 dagars segment</p><p>/</p><p>Unika besökare</p> |
| Sidvyer/unik besökare | Genomsnittligt antal sidor som visas för varje unik besökare på webbplatsen. | <p>Sidvisningar</p><p>/</p><p>Unika besökare</p> |
| Besök/besökare | Genomsnittligt antal besök som en unik besökare gör på webbplatsen. | <p>Besök</p><p>/</p><p>Unika besökare</p> |
| Beräknade unika besökare (ITP 2.1) | <p>För ITP-besökare (användare i Safari-webbläsare) dividerar unika besökare med 2 eller färre.</p><p>Detta förutsätter att du ställer in cookies med JavaScript på klientsidan (inte med en CNAME-implementering). Implementeringar som anger cookies med JavaScript på klientsidan påverkades från och med ITP 2.1. Se: [https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)</p> | <p>Unika besökarmått + ITP-besökare (ITP 2.1, icke-CNAME-implementeringar)</p><p>/</p><p>Unika besökarmått + icke-ITP-besökare (ITP 2.1, icke-CNAME-implementeringar)</p> |
| Sidvyer/beräknade unika besökare (ITP 2.1) | Genomsnittligt antal sidor som visas för beräknade unika besökare (ITP 2.1). | <p>Unika besökarmått + ITP-besökare (ITP 2.1, icke-CNAME-implementeringar)</p><p>/</p><p>Unika besökarmått + icke-ITP-besökare (ITP 2.1, icke-CNAME-implementeringar)</p> |

{style="table-layout:auto"}
