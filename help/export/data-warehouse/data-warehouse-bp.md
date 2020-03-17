---
description: Datalagret har ett flexibelt gränssnitt för att köra anpassade rapporter. Genom att följa dessa riktlinjer kan du minska tiden det tar att hämta data.
keywords: best practices;failure;timeout;troubleshooting
title: Bästa praxis för datalager
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bästa praxis för datalager

Datalagret erbjuder ett flexibelt gränssnitt för att köra anpassade rapporter. Genom att följa dessa riktlinjer kan du minska tiden det tar att hämta data.



| Riktlinje | Beskrivning |
|--- |--- |
| Kör sidvyer, besök, besökare och andra standardrapporter i rapporter och analyser | Innan du skapar en rapport för datalager bör du kontrollera om den information du söker redan finns tillgänglig i rapporter. Om så är fallet kommer rapporten att levereras mycket snabbare tack vare förbearbetningen som utförs av Rapporter och analyser för vanliga mätvärden. |
| Förstå mängden data du begär | En flerårig rapport om ett stort rapportpaket kan innehålla tiotals miljarder datarader. Bearbetning och utvärdering av dessa data kan ta dagar, eller till och med veckor. Utvärdera hur rapporten används för att avgöra om vissa flerårsdata är tillgängliga eller om du kan dela upp rapporten i flera begäranden. |
| Matcha rapportperioden med granulariteten | För rapportgranularitet krävs ytterligare bearbetningstid. Om du rapporterar månadsvis granularitet för ett helt år kommer rapportprocessen att gå mycket snabbare om du skickar in en rapportförfrågan för varje månad. |
| Rapport om slutförda dataintervall | Rapporter om datalager genereras när det begärda datumintervallet har slutförts. Om du till exempel begär en rapport för den aktuella veckan på onsdag, genereras inte rapporten förrän på söndag i nästa vecka. |
| Generera pausrapporter i datalagret | Mått på banor (poster, utgångar, studsar osv.) är inte tillgängliga i datalagret. |
| Virtuella rapportsviter | Datalagerrapportering för virtuella rapportsviter stöder den alternativa tidszon som har konfigurerats i den virtuella rapportsviten. |
