---
description: Ger svar och felsökningsförslag på några av de vanligaste Analytics-frågorna.
keywords: Felsökningsanalys
title: Vanliga frågor om rapporter och analyser
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# Vanliga frågor

{{ra-eol}}

Tillhandahåller svar och felsökningsförslag på några av de vanligaste Analytics-frågorna för rapporter och analyser. Vanliga frågor om implementering finns i [Vanliga frågor](/help/implement/faq.md) i Implementeringshandboken.

+++Mitt konto har låsts; Hur låser jag upp den?
Om du vill återaktivera ett konto kontaktar du en administratör inom organisationen. Se även [Felsöka inloggningsproblem med Adobe Analytics](/help/technotes/troubleshoot-login.md) i Technotes-handboken.
+++

+++Varför ser jag en tom rapport trots att jag vet att data samlas in?
Det finns flera saker att kontrollera för att felsöka rapportdata:

* Kontrollera de mått som används: I vissa rapporter används som standard Intäkter i rapporter och analyser. Kontrollera att mätvärdena som du visar är relevanta för rapporten.
* Kontrollera datumintervallet: Datumintervall, särskilt sådana som ligger utanför organisationens datalagringspolicy, kan inte returnera några data. Kontrollera att datumintervallet är korrekt.
* Kontrollera interna URL-filter: Vissa trafikkällrapporter fungerar inte förrän du har definierat interna URL-filter korrekt.
+++

+++Varför saknas vissa rapporter på navigeringsmenyn?
Rapporter som saknas på en meny kommer oftast från antingen begränsade behörigheter eller anpassade menyer. Kontakta en produktadministratör inom organisationen för att säkerställa att du har tillgång till alla dimensioner och mätvärden som behövs och att menystrukturen för en rapportsvit inte har anpassats.
+++

+++Varför tas vissa långa värden bort?
Nästan alla variabler i Adobe Analytics har en teckengräns. Sidnamnet har en begränsning på 100 tecken, medan anpassade konverteringsvariabler (eVars) har en gräns på 255 tecken. Adobe rekommenderar att du ser till att de värden du skickar till Adobe är kortfattade för att förhindra trunkering.
+++

+++Varför ser jag en stor fördröjning i rapporteringen?
Med realtidsrapportering kan vissa trafikdata vara tillgängliga inom några minuter, medan konvertering och andra bearbetningsintensiva data vanligtvis är tillgängliga inom 30-90 minuter. Även om Experience Cloud-plattformen är robust finns det vissa situationer som kan leda till förseningar i rapporteringen. Den här fördröjningen kallas fördröjning. Se [Latens](/help/technotes/latency.md) i TechNotes-användarhandboken för mer information.
+++

+++Varför kan jag inte se enhetsversionen på iPhone?
Apple-enheter rapporterar sin firmware-version i användaragentsträngen, inte i enhetsversionen. Det är svårt att avgöra vilken version av iPhone som är tillgänglig för Adobe Analytics. Se [Jämföra iPhone enhetsversioner](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) i KB:n för analyser för mer information.
+++

+++Varför matchar inte summorna längst ned i min rapport när jag summerar värdena?
Dimensioner kan ofta användas på flera ställen, Besök som till exempel omfattar midnatt eller flera produkter som tillhör en och samma order. Dimensionsobjektet rapporteras för alla tillämpliga radartiklar, men dedupliceras i rapportens totala belopp. Se [Jämför summan av radobjekt för att rapportera totalt](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) i KB:n för analyser för mer information.
+++

+++Hur utesluter jag data från en viss IP-adress i min rapportserie?
Ni kan ta bort data från interna webbplatsaktiviteter, till exempel platstestning och personalanvändning, från era rapporter. Med den här funktionen kan du och dina kollegor besöka webbplatsen utan att behöva skeva dina trafikdata. Se [Exkludera efter IP-adress](/help/admin/admin/exclude-ip.md) i användarhandboken för Admin om du vill ha mer information.
+++

+++Kan jag ta bort en rapportserie?
Det går inte att ta bort en rapportserie. En rapportsvit kan dock döljas för alla vyer i Adobe Analytics. Observera att serveranrop som skickas till en dold rapportsvit fortfarande räknas in i din månadsgräns. Se [Dölj rapportsviter](/help/admin/company/c-hide-report-suites.md) i användarhandboken för Admin om du vill ha mer information.
+++

+++Vilken behållare ska jag använda när jag använder segmentering? Sidvisning, besök eller besökare?
Segmentbehållaren som du använder beror på hur bred du vill samla in data. Sidvisningsbehållare innehåller bara träffar som matchar segmentkriterierna, vilket är praktiskt när du vill filtrera bort irrelevanta delar av besöken. Besöksbehållare ger dig tillgång till alla träffar på ett besök där ett eller flera träffar de matchande segmentkriterierna, vilket är användbart när du vill titta på sessioner i allmänhet. Besöksbehållare innehåller alla besök där ett träffat villkor för segment är användbart för att titta på människor. Det är ditt val som analytiker för att avgöra vilken segmentbehållare som är bäst att använda. Se [Översikt över segmentering](/help/components/segmentation/seg-overview.md) i användarhandboken för Komponenter om du vill ha mer information.
+++

+++Varför visas inte mitt segment i Data warehouse?
På grund av Data warehouse unika bearbetningsarkitektur är plattformen inte optimerad för att hantera vissa typer av data, som till exempel pathing. Se [data warehouse segmentkompatibilitet](/help/components/segmentation/seg-reference/seg-compatibility.md) i användarhandboken för Komponenter om du vill ha mer information.
+++
