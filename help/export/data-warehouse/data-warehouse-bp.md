---
description: Data warehouse har ett flexibelt gränssnitt för att köra anpassade rapporter. Genom att följa dessa riktlinjer kan du minska tiden det tar att hämta data.
keywords: god praxis;fel;timeout;felsökning
title: Bästa praxis för Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 3%

---

# Bästa praxis för Data Warehouse

data warehouse har ett flexibelt gränssnitt för att köra anpassade rapporter. Genom att följa dessa riktlinjer kan du minska tiden det tar att hämta data.



| Riktlinje | Beskrivning |
|--- |--- |
| Kör sidvyer, besök, besökare och andra standardrapporter i rapporter och analyser | Innan du skapar en Data warehouse-rapport bör du kontrollera om den information du söker redan finns tillgänglig i rapporter. Om så är fallet kommer rapporten att levereras mycket snabbare tack vare förbearbetningen som utförs av Rapporter och analyser för vanliga mätvärden. |
| Förstå mängden data du begär | En flerårig rapport om ett stort rapportpaket kan innehålla tiotals miljarder datarader. Bearbetning och utvärdering av dessa data kan ta dagar, eller till och med veckor. Utvärdera hur rapporten används för att avgöra om vissa flerårsdata är tillgängliga eller om du kan dela upp rapporten i flera begäranden. |
| Matcha rapportperioden med granulariteten | För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad. |
| Rapport om slutförda dataintervall | data warehouse-rapporter genereras när det begärda datumintervallet har slutförts. Om du till exempel begär en rapport för den aktuella veckan på onsdag, genereras inte rapporten förrän på söndag i nästa vecka. |
| Generera rapporter över banor i Data warehouse | Mått på banor (poster, utgångar, studsar osv.) är inte tillgängliga i data warehouse. |
| Virtuella rapportsviter | Rapportering från data warehouse i virtuella rapportsviter har stöd för den alternativa tidszon som har konfigurerats i den virtuella rapportsviten. |
