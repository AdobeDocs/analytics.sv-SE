---
description: Visar information om besökare, t.ex. antal besökare, kundlojalitet och besökaregenskaper.
title: Besöksrapporter
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---


# Besöksrapporter

Visar information om besökare, t.ex. antal besökare, kundlojalitet och besökaregenskaper.

## Återbesöksfrekvens {#concept_447A99B71E484D27A7A02888CC51FD3D}

Visar hur lång tid det tar mellan besök av återkommande besökare och antalet besök som hamnar i varje tidslängdskategori. Använd rapporten för att se hur lång tid det i genomsnitt tar för återkommande besökare att besöka er webbplats, samt trenderna för återkommande kunder.

<!-- 

c_reports_return_freq.xml

 -->

Om du till exempel visar ordermåttet i den här rapporten blir det lättare för en återförsäljare att förstå den mest effektiva tiden mellan besök för att generera konvertering. Använd den här informationen för att effektivt marknadsföra besökare som har gått en viss tid utan att besöka er webbplats.

Ni kan:

* Identifiera antalet återvändande besökare och frekvensen för deras återbesök.
* Utvärdera webbplatsens tilltalande och relevans för besökarna över tid.
* Ta reda på hur klibbig sajten är för besökarna och hur ofta de känner sig tvingade att återvända för ytterligare interaktion eller uppdateringar.
* Identifiera effekten av webbplatsens innehåll och kampanjer för era besökare.

Som standard har den här rapporten följande tidslängder:

* Mindre än en dag
* En till tre dagar
* Tre till sju dagar
* Sju till fjorton dagar
* Fjorton dagar till en månad
* Längre än en månad

## Besöksnummer {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Visar vilka besöksnummer på er webbplats som mest påverkade er framgångsstatistik. En besökare som gör ett första besök på er webbplats räknas med i radartikeln Besök nummer 1. Besökare som återvänder till platsen för ett andra besök räknas i posten Besök nummer 2 o.s.v.

<!-- 

c_reports_visit_number.xml

 -->

Du kan använda den här rapporten som en utfallsrapport för att se om besökarna återvänder. Du kan också lägga till ett intäktsmått för att se om du genererar mer intäkter från inledande besök eller efterföljande besök.

Den här rapporten kan till exempel ge svar på frågor som: Genererade kunder som köpte på sitt fjärde besök fler intäkter än de som köpte vid sitt första besök?

Du kan dela upp den här rapporten med vilken annan rapport eller variabel som helst för att bestämma:

* Hur många besök tar en användare som klickat via kampanj XYZ för att göra ett inköp.
* Om användare i Tokyo till exempel gör fler besök innan de genererar ett lead än användare i London.

>[!NOTE]
>
>Om samma besökare besöker din webbplats flera gånger under samma period, ökas varje angivet besöksnummer för varje besök.

Den här rapporten baseras på besökar-ID-data som skickas till Adobe vid varje besökarträff. När dessa data tas emot jämför Adobe dem med historiska besökar-ID-data för att avgöra om träffen är:

* En ny besökare (Besök nummer är lika med 1).
* En tidigare besökare som fortsätter ett besök (besöksnumret räknas inte upp).
* En tidigare besökare som gjort ett nytt besök (Besök nummer räknas upp med ett).

>[!NOTE]
>
>Varje besökar-ID från Analytics är kopplat till en besökarprofil på Adobes servrar. Besökarprofiler tas bort efter minst 13 månaders inaktivitet, oavsett om en cookie-fil för besöks-ID har gått ut eller inte.

## Kundlojalitet {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Använd den här rapporten för att se om era intäkter påverkas mest av nya kunder eller av återkommande kunder.

<!-- 

c_reports_customerloyalty.xml

 -->

I [!UICONTROL Customer Loyalty] rapporten visas köpmönster för kunder baserat på fyra kategorier av lojalitet:

* **Inte en kund**: Besökare som aldrig har köpt
* **Ny kund**: Besökare som gjorde ett enstaka köp
* **Returkund**: Besökare som gjort 2 inköp
* **Lojala kunder**: Besökare som har köpt 3+

>[!NOTE]
>
>När du använder dessa mått representeras alla användarbesök (eller alla besökare) i den här rapporten, oavsett om besöket (eller besökaren) innehöll ett köp.

Förmånsstatusen ändras efter besökets slut, där en köphändelse inträffar. Exempel: En ny kund (1 köp) gör ett köp och registrerar sig sedan för ett nyhetsbrev efter köpet inom samma besök. Nyhetsbrevets registreringshändelse betraktas fortfarande som en interaktion med nya kunder, eftersom besökarens kundlojalitetsstatus inte ändras förrän vid nästa besök.

## Besökarprofil {#concept_4D829198CD144DCDA667E0651F93AFC7}

Visar information om vilken typ av besökare som kommer till platsen. Du kan se saker som besökarens plats, vilken typ av webbläsare och datormaskinvara som används, vilka språk som används och vilka internetleverantörsdata som är tillgängliga för besökarna.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**: Visar de språk besökarna föredrar, hämtar standardspråket i webbläsaren och visar de språk som besökarna oftast använder på webbplatsen.

**[!UICONTROL Domains]**: Visar en lista över organisationer och Internet-leverantörer som besökarna använder för att komma åt webbplatsen. Den här rapporten skiljer sig från [!UICONTROL Full Domains] rapporten eftersom rapporten Fullständiga domäner registrerar hela ISP-domänen, medan den här rapporten listar den sekundära domänen.

**[!UICONTROL Top Level Domains]**: Identifierar världsregioner som besökare kommer från baserat på deras ursprungliga domäntillägg, och visar hur många besökare som kommer från dessa länder. Domäner som slutar på Commercial (.com), Network (.net), Education (.edu), Government (.gov) och Organization (.org) är vanligtvis baserade i USA och listas separat från de övriga domänerna.

**[!UICONTROL Visitor ZIP/Postal Code]**: Visar de postnummer som producerade kunderna och som hade störst effekt på köpets framgångsmått.

## Geosegmentering {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Visar besökarnas geografiska dynamik i realtid, inklusive länder, delstater och städer som de surfar från. Ni kan också få viktiga insikter om teknologi och preferenser hos er webbplatskarta.
