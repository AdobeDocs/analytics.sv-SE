---
title: Vanliga frågor om attribuering
description: Få svar på vanliga frågor om attribuering.
translation-type: tm+mt
source-git-commit: 06b9ac8ddbfb0398341a2ab5656237e3520a8612
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---


# Vanliga frågor om attribuering

**Vad är radobjektet &quot;Inget&quot; när du använder attribuering?**

Radobjektet Ingen är ett objekt som fångar upp alla konverteringar som har gjorts utan några beröringspunkter i uppslagsfönstret. Försök att inkludera ett längre tidsintervall i rapportfönstret.

**Varför ser jag ibland datum utanför mitt rapporteringsfönster när jag använder attribueringsmodeller?**

Dessa extra datum beror på besökarens rapportfönster. Mer information finns i [Data som visas utanför rapportfönstret](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) i KB för analyser. Adobe planerar att filtrera bort de här extra raderna i en kommande release.

**När ska jag använda ett besöks- eller besöksattribueringsbesök?**

Vilken attribueringslookback du väljer beror på ditt användningssätt. Om konverteringen tar längre tid än ett enda besök rekommenderar vi att besökaren tittar tillbaka. Att skapa ett virtuellt rapportpaket med en längre besöksdefinition är också en potentiell lösning.

**Hur är props och eVars jämfört när man använder attribuering?**

Attribution beräknas om vid rapportkörning, så det finns ingen skillnad mellan prop eller eVar (eller någon annan dimension) för attribueringsmodelleringens skull. Props kan behållas med alla uppslagsfönster eller attribueringsmodeller, och eVar-allokerings-/förfalloinställningar ignoreras.

**Finns det attribueringsmodeller i andra analysfunktioner, som dataflöden eller datalager?**

Nej. I attribueringsmodeller används rapporttidsbearbetning, som bara är tillgänglig i Analysis Workspace. Mer information finns i [Tidsbearbetning](../../../../components/vrs/vrs-report-time-processing.md) för rapport.

**Är attribueringsmodeller bara tillgängliga om jag använder en virtuell rapportsvit med rapporttidsbearbetning aktiverad?**

Attributionsmodeller är tillgängliga utanför virtuella rapportsviter. Även om de använder rapporttidsbearbetning i serverdelen är attribueringsmodeller tillgängliga för både standardrapporteringssviter och virtuella rapportsviter.

**Vilka mått och mätvärden stöds inte?**

Attributpanelen har stöd för alla dimensioner. Mätvärden som inte stöds är:

* Unika besökare
* Besök
* Förekomster
* Sidvyer
* A4T-mått
* Tidsmått
* studsar
* Studsfrekvens
* Poster
* Avslutar
* Sidorna hittades inte
* Sökningar
* Besök på en sida
* Enkel åtkomst

**Kan jag använda ett anpassat uppslagsfönster med mina attribueringsmodeller?**

Ja, med alternativet för anpassat uppslagsfönster kan uppslagsfönster konfigureras till valfritt datumintervall upp till 90 dagar före rapportfönstret. Mer information finns i [Tidsbearbetning](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html) för rapport.

**Fungerar attribuering med klassificeringar?**

Ja, klassificeringar stöds fullt ut.

**Fungerar attribuering med datakällor?**

Ja, de flesta datakällor stöds. Attribuering är inte möjligt med datakällor på sammanfattningsnivå eftersom de inte är kopplade till en besöksidentifierare för Analytics. Datakällor för transaktions-ID stöds också, såvida de inte används i en virtuell rapportsvit med rapporttidsbearbetning aktiverad.

**Fungerar attribuering med Advertising Analytics-integrering?**

Metadata-dimensioner, som matchningstyp och nyckelord, fungerar med attribuering. Mätvärden (inklusive visningar, kostnader, klickningar, genomsnittlig position och medelkvalitet) använder sammanfattningsnivådatakällor och är därför inkompatibla.
