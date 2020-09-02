---
title: Vanliga frågor om attribuering
description: Få svar på vanliga frågor om attribuering.
translation-type: tm+mt
source-git-commit: c206095b8024db0e31586abdf9639fba3401ce3f
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 2%

---


# Vanliga frågor om attribuering

**Vad är radobjektet &quot;Inget&quot; när du använder attribuering?**

Radobjektet Ingen är ett objekt som fångar upp alla konverteringar som sker utan beröringspunkter i uppslagsfönstret. Om du vill minska antalet konverteringar som tilldelats radobjektet Ingen kan du prova att använda ett anpassat uppslagsfönster med en längre uppslagsperiod.

**Varför ser jag ibland datum utanför mitt rapporteringsfönster när jag använder attribueringsmodeller?**

Dessa extra datum beror på besökarens rapportfönster. Mer information finns i [Data som visas utanför rapportfönstret](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) i KB för analyser.

**När ska jag använda besök, besökare eller anpassad attribueringssökning?**

Vilken attribueringslookback du väljer beror på ditt användningssätt. Om konverteringen tar längre tid än ett besök rekommenderar vi besökare eller anpassat uppslag. För längre konverteringscykler är anpassade uppslagsfönster bäst eftersom de är den enda typ som kan hämta in data från före rapportfönstret

**Hur är props och eVars jämfört när man använder attribuering?**

Attribution beräknas om vid rapportkörning, så det finns ingen skillnad mellan ett prop eller en eVar (eller någon annan dimension) för attribueringsmodelleringens skull. Props kan finnas kvar med alla uppslagsfönster eller attribueringsmodeller, och eVar allokerings-/förfalloinställningar ignoreras.

**Finns det några attribueringsmodeller i andra analysfunktioner, som dataflöden eller Data warehouse?**

Nej. I attribueringsmodeller används rapporttidshantering, som bara är tillgänglig i Analysis Workspace. Mer information finns i [Tidsbearbetning](/help/components/vrs/vrs-report-time-processing.md) för rapport.

**Är attribueringsmodeller bara tillgängliga om jag använder en virtuell rapportsvit med rapporttidsbearbetning aktiverad?**

Attributionsmodeller är tillgängliga utanför virtuella rapportsviter. Även om de använder rapporttidsbearbetning i serverdelen är attribueringsmodeller tillgängliga för både standardrapporteringssviter och virtuella rapportsviter.

**Vilka mått och mätvärden stöds inte?**

Attributpanelen har stöd för alla dimensioner. Mätvärden som inte stöds är:

* Alla beräknade värden
* Unika besökare
* Besök
* Förekomster
* Sidvisningar
* A4T-mått
* Tidsmått
* Studsar
* Studsfrekvens
* Första besökssida
* Sista besökssida
* Sidor som inte hittades
* Sökningar
* Besök på en sida
* Enkelt besök

**Fungerar attribuering med klassificeringar?**

Ja, klassificeringar stöds fullt ut.

**Fungerar attribuering med datakällor?**

Ja, de flesta datakällor stöds. Attribuering är inte möjligt med datakällor på sammanfattningsnivå eftersom de inte är kopplade till en besöksidentifierare för Analytics. Datakällor för transaktions-ID stöds också, såvida de inte används i en virtuell rapportsvit med rapporttidsbearbetning aktiverad.

**Fungerar attribuering tillsammans med Advertising Analytics?**

Metadata-dimensioner, som matchningstyp och nyckelord, fungerar med attribuering. Mätvärden (inklusive visningar, kostnader, klickningar, genomsnittlig position och medelkvalitet) använder sammanfattningsnivådatakällor och är därför inkompatibla.

**Hur fungerar attribuering med marknadsföringskanaler?**

När marknadsföringskanalerna lanserades för första gången fick de bara första och sista touch-dimensioner. Explicit första/sista beröringsdimensioner behövs inte längre med den aktuella versionen av attribuering. Adobe har allmänna dimensioner av typen&quot;Marknadsföringskanal&quot; och&quot;Marknadsföringskanal&quot; så att du kan använda dem med den önskade attribueringsmodellen. Dessa generiska dimensioner fungerar på samma sätt som Senaste beröringskanal, men är märkta annorlunda för att förhindra förvirring när marknadsföringskanaler med en annan attribueringsmodell används.

Eftersom dimensionerna för marknadsföringskanalen är beroende av en traditionell besöksdefinition (som definieras av deras bearbetningsregler), kan deras besöksdefinition inte ändras med hjälp av virtuella rapportsviter.

**Hur fungerar attribuering med flervärdesvariabler som listvariabler?**

Vissa dimensioner i Analytics kan innehålla flera värden för en enda träff. Vanliga exempel är listvar och variabeln products.

När attribuering tillämpas på träffar med flera värden får alla värden i samma träff samma kredit. Eftersom många värden kan ta emot krediten kan rapportsumman vara annorlunda än om du summerade varje enskild radartikel. Rapportsumman dedupliceras medan varje enskild dimensionspost får rätt kredit.

**Hur fungerar attribuering med segmentering?**

Attribuering körs alltid före segmentering, och segmentering körs innan rapportfilter tillämpas. Detta koncept gäller även virtuella rapportsviter som använder segment.

Om du till exempel skapar ett VRS med segmentet &quot;Visa träffar&quot; kan du se andra kanaler i en tabell med hjälp av vissa attribueringsmodeller.

![Virtuellt rapportpaket endast för visning](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Om ett segment undertrycker träffar som innehåller dina mått, kommer dessa metriska instanser inte att tillskrivas någon dimension. Ett liknande rapportfilter döljer bara vissa dimensionsobjekt, utan att påverka de värden som bearbetas enligt attribueringsmodellen. Därför kan ett segment returnera lägre värden än ett filter med en jämförbar definition.
