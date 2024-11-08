---
title: Besök
description: En sekvens med sidvyer i ett möte.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: fb25807a0f34409bb3a27f344ff7508a9dd414a4
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 0%

---

# Besök

Besöken [](overview.md) visar antalet sessioner för alla besökare på webbplatsen.

## Hur det här måttet beräknas

Ett besök hör alltid till en tidsperiod, så du vet om du ska räkna med ett nytt besök om samma person kommer tillbaka till din webbplats. Ett besök börjar när användaren först kommer till din webbplats. Ett besök avslutas när något av följande villkor uppfylls:

* **30 minuters inaktivitet**: Nästan alla sessioner avslutas på det här sättet. Om det tar mer än 30 minuter mellan träffarna börjar ett nytt besök.
* **12 timmars aktivitet**: Om en användare konsekvent utlöser bildbegäranden utan 30 minuters mellanrum i mer än 12 timmar, startar ett nytt besök automatiskt.
* **2500 träffar**: Om en användare genererar ett stort antal träffar utan att starta en ny session räknas ett nytt besök efter 2 500 bildförfrågningar.
* **100 träffar på 100 sekunder**: Om ett besök har fler än 100 träffar under de första 100 sekunderna av besöket avslutas besöket automatiskt. Detta beteende indikerar vanligtvis båda aktiviteterna och begränsningen används för att öka rapportens prestanda.

Ett besök sammanfaller inte nödvändigtvis med en webbläsarsession på grund av ovanstående kriterier. En av de vanligaste skillnaderna är var en besökare navigerar till webbplatsen, lämnar fliken öppen i mer än 30 minuter och sedan fortsätter surfningen. Även om denna åtgärd tekniskt sett ingår i samma surfsession anser Adobe att denna åtgärd är två separata besök.

## Beteende som påverkar besök

Om en besökare utför någon av dessa åtgärder, kommer ett nytt besök att påbörjas:

* Tar bort deras cookies-sessioner och fortsätter surfa på webbplatsen
* Lämnar webbplatsen öppen på en flik i mer än 30 minuter och fortsätter sedan att bläddra
* Öppnar en annan webbläsare och navigerar till din webbplats på samma dator
* Samma person som surfar på din webbplats på olika enheter

Om en besökare utför någon av dessa åtgärder börjar ett nytt besök **inte** så länge det är mindre än 30 minuter mellan efterföljande träffar:

* Stänger webbläsaren och navigerar sedan till webbplatsen igen
* Startar om datorn, öppnar samma webbläsare och navigerar till webbplatsen igen
* Övergångar till ett annat nätverk, t.ex. frånkoppling från en dockningsstation för kabelanslutet nätverk till ett trådlöst nätverk
* Bläddrar på webbplatsen på flera flikar. Om en besökare växlar fram och tillbaka mellan flikar räknas varje träff som en del av samma besök.

## Ändra definitionen för ett besök

Du kan ändra definitionen för ett besök till en annan tidpunkt än 30 minuter.

* För [virtuella rapportsviter](../vrs/vrs-about.md) kan du ändra tidsgränsen för besök (tiden mellan träffarna som startar ett nytt besök) med hjälp av listrutan [!UICONTROL Visit timeout]. Du kan ändra tidsgränsen för besök till ett rimligt värde.
* Kontakta kundtjänst om du vill begära att tidsgränsen för ett besök (tiden mellan träffarna som startar ett nytt besök) förkortas för en viss rapportserie. Besök tidsgränsen för standardrapportsviter så att du bara kan korta ned den i 30 minuter.

## Besök som sträcker sig över en datumgräns

Ett besök räknas för varje berörd tidsperiod. Om du till exempel har en besökare som börjar navigera på webbplatsen måndag klockan 11:45 och sedan skickar sin senaste bildförfrågan tisdag klockan 12:10, ser du ett besök som tillskrivs både måndag och tisdag. Den totala besöksstatistiken är dock borttagen och visar ett enda besök för projektets datumintervall.

## Besök på en dimension jämfört med totalt antal besök

Besök i samband med en dimension (till exempel [Marknadskanal](../dimensions/marketing-channel.md)) visar antalet besök som innehåller en viss dimensionspost vid något tillfälle. Det finns ofta flera dimensionsobjekt i olika träffar på samma besök. Försök att summera besök som rapporterar om dimensionsobjekt är vanligtvis inte rimligt.

## Besök alla besökare i Datan Warehouse

Måttet Besök - alla besökare är tillgängligt i Data Warehouse utöver Visits-måttet. Mätvärdet &#39;Besök - alla besökare&#39; är jämförbart med mätvärdet &#39;Besök&#39; i andra analysverktyg. Mätvärdet för &#39;Besök&#39; i Datan Warehouse utesluter besökare som inte har beständiga cookies. Adobe rekommenderar att du använder &#39;Besök - alla besökare&#39; i en Data Warehouse där besök önskas som mätvärden.
