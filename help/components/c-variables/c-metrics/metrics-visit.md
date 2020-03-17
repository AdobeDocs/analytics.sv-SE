---
description: En sekvens med sidvyer i ett möte. Besöksmåtten används ofta i rapporter som visar antalet användarsessioner under den valda tidsperioden.
keywords: visit
title: Besök
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Besök

En sekvens med sidvyer i ett möte. Besöksmåtten används ofta i rapporter som visar antalet användarsessioner under den valda tidsperioden.

> [!NOTE] Information om hur besök och öppningar av mobilappar beräknas finns i [Jämför besök och starter](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) av mobilappar i kunskapsbasen.

Besöken är alltid kopplad till en tidsperiod, så du vet om du ska räkna med ett nytt besök om samma besökare kommer tillbaka till din webbplats. En session startar när användaren först kommer till din webbplats och slutar i något av följande scenarier:

* **30 minuters inaktivitet:** Nästan alla sessioner avslutas på det här sättet. Om det har gått mer än 30 minuter mellan bildförfrågningarna påbörjas ett nytt besök.
* **12 timmars konsekvent aktivitet:** Om en användare begär bilder utan ett mellanrum på mer än 30 minuter i 12 timmar, startar ett nytt besök automatiskt.
* **2 500 träffar:** Om en användare skapar ett stort antal träffar utan att starta en ny session räknas ett nytt besök efter 2 500 bildförfrågningar.
* **100 träffar på 100 sekunder**: Om ett besök består av fler än 100 träffar på mindre än 100 sekunder avslutas besöket automatiskt. Detta beteende indikerar vanligtvis båda aktiviteterna och begränsningen tillämpas för att förhindra att dessa bearbetningsintensiva besök ökar fördröjningen och ökar tiden det tar att generera rapporter.

> [!NOTE] Definitionen av ett besök kan förkortas för en rapportserie om det efterfrågas, men den kan inte förlängas. Be någon av organisationens användare kontakta Kundtjänst för att begära denna ändring.

Följande scenarier startar inte ett nytt besök:

* Användaren stänger fliken, öppnar den igen och går tillbaka till webbplatsen inom 30 minuter. Användaren kan också stänga webbläsaren eller starta om datorn och ändå räknas som ett enda besök (förutsatt att besökaren kommer tillbaka till webbplatsen inom 30 minuter).
* Användare som bläddrar på din webbplats på flera flikar. Även om surfning med flera flikar inte ökar antalet besök eller besökare, gör en separat webbläsare det. Det beror på att de olika flikarna refererar till samma cookies, medan separata webbläsare inte gör det.

Ett besök sammanfaller inte nödvändigtvis med en webbläsarsession. Om en besökare till exempel stänger webbläsaren, öppnar webbläsaren igen och kommer till webbplatsen fem minuter senare, känns det som en fortsättning på samma besök. Det innebär också att om en besökare stannar kvar på en sida i 35 minuter kommer besöket att ha stängts och bearbetats, och ett nytt besök kommer att påbörjas om de klickar till en annan sida.

När ett besök avslutas kommer alla variabler med en besöksförfallotid att upphöra och inte längre finnas kvar. Besöksnumret kommer att höjas vid besökarens nästa besök.

> [!NOTE] Om du använder Analytics som rapportkälla för Adobe Target kan du läsa [Minimera antalet uppblåsta besök och besöksräknare i A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) i [!DNL Target] dokumentationen.

Mer information finns i [Identifiera unika besökare](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html) i implementeringsguiden för Adobe Analytics.

**Tidsperioder**

Ett besök rapporteras under varje tidsperiod som aktiviteten inträffade. Anta till exempel att ett besök börjar 11.45 den 1 december och fortsätter till 23.30 den 2 december. Besöken räknas den 1 december och den 2 december. Denna rapportering gäller andra tidsperioder, inklusive veckovisa, månadsvisa, kvartalsvisa och årsvisa.
