---
title: Besök
description: En sekvens med sidvisningar under en session.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '530'
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

Ett besök sammanfaller inte nödvändigtvis med en webbläsarsession på grund av ovanstående kriterier. En av de vanligaste skillnaderna är var en besökare navigerar till webbplatsen, lämnar fliken öppen i mer än 30 minuter och sedan fortsätter surfningen. Även om den här åtgärden tekniskt sett ingår i samma webbläsarsession anser Adobe att den här åtgärden är två separata besök.

## Ändra definitionen för ett besök

Du kan ändra definitionen för ett besök till en annan tidpunkt än 30 minuter.

* För [virtuella rapportsviter](../vrs/vrs-about.md)kan du ändra tidsgränsen för besök med [!UICONTROL Visit timeout] listrutan. Du kan ändra tidsgränsen för besök till ett rimligt värde.
* Om du vill ha en standardrapport kontaktar du Kundtjänst för att begära att besökslängden ska förkortas för en viss rapportserie. Du kan bara korta ned längden för standardrapportsviter med 30 minuter.

## Beteende som påverkar besök

Om en besökare utför någon av dessa åtgärder, kommer ett nytt besök att påbörjas:

* Rensar deras cachesession och fortsätter surfa på webbplatsen
* Lämnar webbplatsen öppen på en flik i mer än 30 minuter och fortsätter sedan att surfa
* Öppnar en annan webbläsare och navigerar till din webbplats på samma dator
* Samma person som surfar på din webbplats på olika enheter

Om en besökare utför något av dessa åtgärder börjar ett nytt besök **inte** så länge det är mindre än 30 minuter mellan efterföljande träffar:

* Stänger webbläsaren och navigerar sedan till webbplatsen igen
* Startar om datorn, öppnar samma webbläsare och navigerar till webbplatsen igen
* Övergångar till ett annat nätverk, t.ex. frånkoppling från en dockningsstation för kabelanslutet nätverk till ett trådlöst nätverk
* Bläddrar på webbplatsen på flera flikar. Om en besökare växlar fram och tillbaka mellan flikar räknas varje träff som en del av samma besök.

## Besök som sträcker sig över en datumgräns

Ett besök räknas för varje berörd tidsperiod. Om du till exempel har en besökare som börjar navigera på webbplatsen måndag klockan 11:45 och sedan skickar sin senaste bildförfrågan tisdag klockan 12:10, ser du ett besök som tillskrivs både måndag och tisdag. Den totala besöksstatistiken är dock borttagen och visar ett enda besök för projektets datumintervall.
