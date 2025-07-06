---
title: Vanlig fråga om attribuering
description: Få svar på vanliga frågor om attribuering.
feature: Attribution
role: User, Admin
exl-id: 8e05957a-f954-4e61-aeed-cd2bd2fe11f8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 1%

---

# Frågor och svar

Här är svar på vanliga frågor om attribuering.

++## Vad är radobjektet **[!UICONTROL None]** när attribuering används?

Radobjektet Ingen är ett objekt som fångar upp alla konverteringar som sker utan beröringspunkter i uppslagsfönstret. Om du vill minska antalet konverteringar som tilldelats radobjektet Ingen kan du prova att använda ett anpassat uppslagsfönster med en längre uppslagsperiod.

+++


++## Varför ser jag datum utanför mitt rapporteringsfönster när jag använder attribueringsmodeller?

Vissa besöksbaserade mätvärden, som [Poster](/help/components/metrics/entries.md) eller [Studsfrekvens](/help/components/metrics/bounce-rate.md), kan attribuera data till en period före rapportfönstrets startdatumintervall. Den här situationen beror på attribueringsmodeller som använder ett uppslagsfönster, som avgör hur långt bakåtattribueringen ska vara för att ge betyg för mätvärden. Det vanligaste scenariot är när besök sträcker sig över midnatt. Exempel:

1. En användare besöker din hemsida kl. 23.55 den 7 september.
1. De besöker flera sidor, varav det sista inträffade kl. 8.05.
1. En vecka senare kommer du att köra en rapport med en daglig trendfrekvens mellan 8 och 14 september.

Träffbaserade mätvärden, som [Sidvyer](/help/components/metrics/page-views.md), skulle generera förväntade utdata, data som trendas varje dag från 8 september till 14 september. Besöksbaserade mätvärden visar dock även ovanstående besök den 7 september. Besöken fick sitt tillskrivna inlägg den 7 september, och som standard är återsökningsfönstret 1 september-31 september.

Studsfrekvensen visar alltid 0 % den 7 september i detta exempel. Det här måttet definieras som `Bounces divided by Entries`, ett träffbaserat mätvärde delat med ett besöksbaserat mätvärde. Satser består av en enda bildbegäran, så de kan inte sträcka sig över flera dagar. Eventuella studsar den 7 september inträffade utanför rapportfönstret, vilket orsakade den garanterade studsfrekvensen på 0 % för den dagen. Andra träffbaserade mätvärden skulle också visa 0 för den 7 september i den här rapporten, eftersom dessa träffar inte heller ligger inom rapportfönstret.

Se ett annat liknande exempel. Den enda skillnaden mellan följande exempel och ovanstående exempel är datumen:

1. En användare besöker din hemsida kl. 23.55 den 31 augusti.
1. De besöker flera sidor, varav det sista inträffade kl. 12.05 den 1 september.
1. En vecka senare körs en rapport med en daglig trendfrekvens mellan 1 september och 7 september.

I det här exemplet visar inte Tävlingsbidrag och Studsfrekvens data från 31 augusti. Fönstret för sökning och rapportering börjar båda den 1 september, så det går inte att tilldela data från den 31 augusti.

+++


<!-- not relevant anymore due to introduction of separation of container and lookback window 
+++## When should I use a visit, visitor, or custom attribution lookback?

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor or custom lookback is recommended. For longer conversion cycles, custom lookback windows are best as they are the only type that can pull in data from prior to the reporting window.

+++
-->

++## Hur fungerar props och eVars när man använder attribuering?

Attribution beräknas om vid rapportkörning, så det finns ingen skillnad mellan ett prop eller eVar (eller någon annan dimension) för attribueringsmodelleringens skull. Props kan finnas kvar i alla uppslagsfönster eller attribueringsmodeller, och eVar inställningar för allokering/förfallodatum ignoreras.

+++


+++## Finns det attribueringsmodeller i andra analysfunktioner, som Data Feeds eller Data Warehouse?

Nej. I attribueringsmodeller används rapporttidshantering, som bara är tillgänglig i Analysis Workspace. Mer information finns i [Tidsbearbetning för rapport](/help/components/vrs/vrs-report-time-processing.md).

+++


+++# Är attribueringsmodeller bara tillgängliga om jag använder en virtuell rapportsvit med rapporttidsbearbetning aktiverad?

Attributionsmodeller är tillgängliga utanför virtuella rapportsviter. Även om de använder rapporttidsbearbetning i serverdelen är attribueringsmodeller tillgängliga för både standardrapporteringssviter och virtuella rapportsviter.

+++


++## Vilka mått och mått stöds inte?

Attributpanelen har stöd för alla dimensioner. Mätvärden som inte stöds är:

* Alla beräknade värden
* Unika besökare
* Besök
* Förekomster
* Sidvisningar
* A4T-mått
* Tidsåtgång - mått
* Studsar
* Studsfrekvens
* Poster
* Avslutar
* Sidorna hittades inte
* Sökningar
* Besök på en sida
* Enkel åtkomst

+++


++## Fungerar attribuering med klassificeringar?

Ja, klassificeringar stöds fullt ut.

+++


++## Fungerar attribuering med datakällor?

Ja, de flesta datakällor stöds. Attribution is not possible with summary-level data sources because these data sources does not attach to an Analytics visitor identifier.

Datakällor för transaktions-ID behandlas som alla andra träffar. Transaktions-ID-datakällor använder inte den särskilda bearbetning som normalt används i traditionell rapportering. När du använder rapporttidsbearbetning har transaktions-ID-träffar med andra ord eVar-värden som har spridits från träffar som inträffar nära tidsstämpeln för träff i transaktions-ID. Värdena sprids inte från träffar som inträffade nära tidpunkten för den ursprungliga transaktionen.

När det är möjligt är attribueringen beroende av MID-kolumnvärdet som skickas inom en händelse i datakällan, i stället för ett beständigt värde. Attributmodellen tillämpas direkt på MID-kolumnvärdena i datakällan. När du till exempel använder [Senaste Touch-attribuering](models.md) startar modellen från varje instans av ett mätresultat. Och går bakåt sekventiellt i träffarna tills modellen når det senaste värdet som observerats i MID-kolumnen.

Om det inte är möjligt används MID-värdet i den *föregående posten* i datakällan för utvärdering. Denna tidigare post kanske inte beställs sekventiellt via tidsstämpel eftersom AA inte stöder data som ligger utanför ordningen.

På grund av att posterna inte ordnas sekventiellt kan de förväntade värdena från att tillämpa beständighet påverka den tid som finns mellan den angivna transaktions-ID-tidsstämpeln och den ursprungliga transaktionen.

+++


++## Fungerar attribuering med Advertising Analytics-integrering?

Metadata-dimensioner, som matchningstyp och nyckelord, fungerar med attribuering. Mätvärden (inklusive visningar, kostnader, klickningar, genomsnittlig position och medelkvalitet) använder sammanfattningsnivådatakällor och är därför inkompatibla.

+++


+++## Hur fungerar attribuering med marknadsföringskanaler?

När marknadsföringskanalerna lanserades för första gången fick de bara första och sista touch-dimensioner. Explicit första/sista beröringsdimensioner behövs inte längre med den aktuella versionen av attribuering. Adobe tillhandahåller generiska dimensioner för [!UICONTROL Marketing Channel] och [!UICONTROL Marketing Channel Detail] så att du kan använda dem med den önskade attribueringsmodellen. Dessa generiska dimensioner är identiska med [!UICONTROL Last Touch Channel] dimensioner, men de är märkta annorlunda för att förhindra förvirring när marknadsföringskanaler med en annan attribueringsmodell används.

Eftersom dimensionerna för marknadsföringskanalen är beroende av en traditionell besöksdefinition (som definieras av deras bearbetningsregler), kan deras besöksdefinition inte ändras med hjälp av virtuella rapportsviter.

+++


++## Hur fungerar attribuering med variabler med flera värden, till exempel listvariabler?

Vissa dimensioner i Analytics kan innehålla flera värden för en enda träff. Vanliga exempel är listvar och variabeln products.

När attribuering tillämpas på träffar med flera värden får alla värden i samma träff samma kredit. Eftersom många värden kan ta emot krediten kan rapportsumman vara annorlunda än om du summerade varje enskild radartikel. Rapportsumman dedupliceras medan varje enskild dimensionspost får rätt kredit.

+++


++## Hur fungerar attribuering med segmentering?

Attribuering körs alltid före segmentering, och segmentering körs innan rapportfilter tillämpas. Detta koncept gäller även virtuella rapportsviter som använder segment.

Om du t.ex. skapar en virtuell rapportserie med segmentet &quot;Visa träffar&quot; kan du se andra kanaler i en tabell med hjälp av vissa attribueringsmodeller.

![Virtuellt rapportpaket som bara kan visas](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Om ett segment undertrycker träffar som innehåller dina mätvärden, tillskrivs de inte någon dimension. Ett liknande rapportfilter döljer emellertid helt enkelt vissa dimensionsobjekt, utan att det påverkar de mätvärden som bearbetas enligt attribueringsmodellen. Därför kan ett segment returnera lägre värden än ett filter med en jämförbar definition.

+++
