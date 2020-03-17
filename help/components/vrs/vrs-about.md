---
description: Virtuella rapportsviter segmenterar era Adobe Analytics-data så att ni kan styra åtkomsten till varje segment.
title: Översikt över virtuella rapportsviter
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Översikt över virtuella rapportsviter

Virtuella rapportsviter segmenterar era Adobe Analytics-data så att ni kan styra åtkomsten till varje segment.

Många kunder har data som flödar in i ett globalt rapporteringsprogram, men har också data som flödar in i mindre rapporteringsprogram. De ställer in en variabel på flera rapportsviter och skickar data till mer än en rapportserie. Detta kallas för *multisuite-taggning* eller *bas-/överordnad rapportserie*.

Alla data kan till exempel samlas in i en rapportsserie, men sedan kan du skapa en sekundär rapportserie så att andra personer i företaget har tillgång till en del av informationen, men inte hela. Data kan delas upp efter region. Du kan ha olika webbplatser för olika länder. Andra exempel kan vara specifika varumärken som tillhör ett större företag, men som har sina egna marknadsföringsteam.

Med ett *virtuellt rapporteringsprogram* (VRS) kan ni återskapa detta förgreningskoncept med hjälp av segment i stället för flera rapportsviter. Data skickas till en rapportserie och delas sedan upp efter segment. Med hjälp av exemplet med flera varumärken kan du ange ett värde för varumärket som ett objekt tillhör. Med hjälp av segment kan du rapportera objekten som tilldelats varje säljprojekt. Var och en av dessa segment får en egen bild och skapar effektivt en ny rapportserie. Du skickar inte data specifikt till det segmentet, bara till den globala rapportsviten, men den fungerar i dina rapporter som om det vore en annan rapportserie.

En virtuell rapportsvit ärver de flesta tjänstenivåerna i basrapportsviten, som eVar-inställningar, bearbetningsregler, klassificeringar osv. Följande inställningar ärvs INTE:

* Rapportsvit-ID (RSID)
* Rapportsvitens namn
* Behörighetsgrupper (virtuella rapportsviter kan tilldelas egna behörighetsgrupper)

## Fördelar med virtuella rapportsviter {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Kunderna betalar för sekundära serversamtal, så om du tar bort dessa samtal kan det leda till betydande besparingar. En virtuell rapportsvit är också helt retroaktiv. Om den globala rapportsviten redan innehåller data inkluderas relevanta data automatiskt i en ny virtuell rapportserie. En ny sekundär rapportserie börjar samla in data först när den har skapats, så den innehåller inga historiska data. När ni implementerar Analytics behöver ni bara skicka data till en rapportsvit, i stället för att behöva skapa implementeringar för den globala rapportsviten och varje sekundär rapportsvit.

Virtuella rapportsviter - hjälp:

* Förenkla implementeringen genom att använda ett enda RSID (Report Suite ID) för alla webbplatser/domäner. Genom att ha alla data i en enda rapportsserie kan vi ta fram kundanalyser när vi går mot nästa generation av Adobe Analytics.
* Affärsanvändare i organisationen ser alltid bara de datasegment som är relevanta för dem.
* Förbättra säkerheten genom att ge administratörsanvändare möjlighet att styra dataåtkomsten enklare och exaktare efter implementeringen.
* Möjlighet att delta i Device Co-op
* Personmått
* En enkundsvy över data (i framtiden)
* Möjlighet att skapa ett obegränsat antal virtuella rapportsviter för att segmentera data

## Begränsningar för virtuella rapportsviter {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Virtuella rapportsviter har följande begränsningar:

* Eventuella begränsningar för segment gäller för virtuella rapportsviter

   En virtuell rapportsvit är inget annat än ett segment som används i en rapportsvit. Eftersom varje rapportsvit har ett eget datalager och sin egen datafeed, ger flera rapportsviter vissa fördelar som segment inte ger.
* Realtidsrapport
* Inställningar och variabelnamn kan inte anpassas på samma sätt i en fullständig rapportserie

## Virtual Report Suites vs. Multisuite Taggning {#section_317E4D21CCD74BC38166D2F57D214F78}

| Funktion | Virtual Report Suite | Märken för flera programsviter |
|--- |--- |--- |
| Ger realtidsrapportering eller&quot;aktuella data&quot;-rapportering | Nej | Ja |
| Fungerar i alla analysverktyg (Analysis Workspace, Report Builder, Ad Hoc Analysis, osv.) | Ja.   Obs!  Du kan bara redigera och identifiera dem som virtuella rapportsviter i Rapporter och analyser. Du kan dock välja dem i listrutorna för rapportsviten i de andra verktygen. | Ja |
| Kan överföra data till den (via klassificeringar, dataflöden osv.) | Nej | Ja |
| Stöder skapande av DL-rapporter, bokmärken, instrumentpaneler, mål, aviseringar, segment, beräknade mätvärden... | Ja | Ja |
| Kan läggas till individuellt i behörighetsgrupper | Ja | Ja |
| Kan använda administratörsfunktioner för att ändra enskilda inställningar för den här rapportsviten (Admin > Rapportsviter) | Nej (inställningarna ärvs från överordnad) | Ja |

## Kombinera Virtual Report Suites och Multisuite Tagging {#section_026FA3FCD7314DD18220E73EC5702AFF}

I vissa fall finns det fördelar med att använda både virtuella rapportsviter och taggning för flera programsviter.

En återförsäljare kan till exempel använda en rapportsserie för varje varumärke och virtuella rapportsviter för varje varumärke för att dela upp data per region. På samma sätt kan en atletisk organisation använda en rapportserie för varje team och sedan virtuella rapportsviter för att dela in fansen i teamets region från dem utanför regionen.
