---
title: Besök
description: En sekvens med sidvisningar under en session.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 1%

---

# Besök

Mätvärdet &quot;Besök&quot; visar antalet sessioner för alla besökare på webbplatsen.

## Hur det här måttet beräknas

Ett besök hör alltid till en tidsperiod, så du vet om du ska räkna med ett nytt besök om samma person kommer tillbaka till din webbplats. Ett besök börjar när användaren först kommer till din webbplats. Ett besök avslutas när något av följande villkor uppfylls:

* **30 minuters inaktivitet**: Nästan alla sessioner avslutas på det här sättet. Om det tar mer än 30 minuter mellan träffarna börjar ett nytt besök.
* **12 timmars aktivitet**: Om en användare konsekvent skickar bildförfrågningar utan 30 minuters mellanrum i mer än 12 timmar, startar ett nytt besök automatiskt.
* **2 500 träffar**: Om en användare skapar ett stort antal träffar utan att starta en ny session räknas ett nytt besök efter 2 500 bildförfrågningar.
* **100 träffar på 100 sekunder**: Om ett besök består av fler än 100 träffar på mindre än 100 sekunder avslutas besöket automatiskt. Detta beteende indikerar vanligtvis båda aktiviteterna och begränsningen används för att öka rapportens prestanda.

Ett besök sammanfaller inte nödvändigtvis med en webbläsarsession på grund av ovanstående kriterier. En av de vanligaste skillnaderna är var en besökare navigerar till webbplatsen, lämnar fliken öppen i mer än 30 minuter och sedan fortsätter surfningen. Även om denna åtgärd tekniskt sett ingår i samma surfsession anser Adobe att denna åtgärd är två separata besök.

## Beteende som påverkar besök

Om en besökare utför någon av dessa åtgärder, kommer ett nytt besök att påbörjas:

* Rensar deras cachesession och fortsätter surfa på webbplatsen
* Lämnar webbplatsen öppen på en flik i mer än 30 minuter och fortsätter sedan att surfa
* Öppnar en annan webbläsare och navigerar till din webbplats på samma dator
* Samma person som surfar på din webbplats på olika enheter

Om en besökare utför någon av dessa åtgärder gör ett nytt besök **not** starta så länge som det är mindre än 30 minuter mellan efterföljande träffar:

* Stänger webbläsaren och navigerar sedan till webbplatsen igen
* Startar om datorn, öppnar samma webbläsare och navigerar till webbplatsen igen
* Övergångar till ett annat nätverk, t.ex. frånkoppling från en dockningsstation för kabelanslutet nätverk till ett trådlöst nätverk
* Bläddrar på webbplatsen på flera flikar. Om en besökare växlar fram och tillbaka mellan flikar räknas varje träff som en del av samma besök.

## Ändra definitionen för ett besök

Du kan ändra definitionen för ett besök till en annan tidpunkt än 30 minuter.

* För [Virtuella rapportsviter](../vrs/vrs-about.md)kan du ändra tidsgränsen för besök med [!UICONTROL Visit timeout] listruta. Du kan ändra tidsgränsen för besök till ett rimligt värde.
* Om du vill ha en standardrapport kontaktar du Kundtjänst för att begära att besökslängden ska förkortas för en viss rapportserie. Du kan bara korta ned längden för standardrapportsviter med 30 minuter.

## Besök som sträcker sig över en datumgräns

Ett besök räknas för varje berörd tidsperiod. Om du till exempel har en besökare som börjar navigera på webbplatsen måndag klockan 11:45 och sedan skickar sin senaste bildförfrågan tisdag klockan 12:10, ser du ett besök som tillskrivs både måndag och tisdag. Den totala besöksstatistiken är dock borttagen och visar ett enda besök för projektets datumintervall.

## Besök på en dimension jämfört med totalt antal besök

Besök i samband med en dimension (t.ex. [Marknadsföringskanal](../dimensions/marketing-channel.md)) visar antalet besök som vid något tillfälle innehöll en viss dimensionspost. Det finns ofta flera dimensionsobjekt i olika träffar på samma besök. Försök att summera besök som rapporterar om dimensionsobjekt är vanligtvis inte rimligt.

## Besök alla besökare i Data warehouse

Måttet Besök - Alla besökare är tillgängligt i Data warehouse utöver Visits-måttet. Mätvärdet &#39;Besök - alla besökare&#39; är jämförbart med mätvärdet &#39;Besök&#39; i andra analysverktyg. Mätvärdet &#39;Besök&#39; i Data warehouse utesluter besökare som inte har beständiga cookies. Adobe rekommenderar att du använder &#39;Besök - alla besökare&#39; i Data warehouse där besök önskas som mätvärden.
