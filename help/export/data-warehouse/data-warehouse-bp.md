---
description: Lär dig riktlinjerna som minskar tiden det tar att hämta in data från Datan Warehouse.
keywords: god praxis;fel;timeout;felsökning
title: Bästa praxis för Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Bästa praxis för Data Warehouse

Data Warehouse är ett flexibelt gränssnitt för att köra anpassade rapporter. Använd följande riktlinjer för att minska tiden det tar att hämta data:

| Riktlinje | Beskrivning |
|--- |--- |
| Förstå mängden data du begär | En flerårig rapport om ett stort rapportpaket kan innehålla tiotals miljarder datarader. Bearbetning och utvärdering av dessa data kan ta dagar, eller till och med veckor. Utvärdera hur rapporten används för att avgöra om vissa flerårsdata är tillgängliga eller om du kan dela upp rapporten i flera begäranden. |
| Matcha rapportperioden med granulariteten | För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad. |
| Rapport om slutförda dataintervall | Rapporter om Data Warehouse genereras när det begärda datumintervallet är slutfört. Om du till exempel begär en rapport för den aktuella veckan på onsdag, genereras inte rapporten förrän på söndag i nästa vecka. |
| Generera rapporter om kundvägar i Data Warehouse | Mått på banor (poster, utgångar, studsar osv.) är inte tillgängliga i datalagret. |
| Virtuella rapportsviter | Rapportering av Data Warehouse på virtuella rapportsviter har stöd för den alternativa tidszon som har konfigurerats på den virtuella rapportsviten. |

