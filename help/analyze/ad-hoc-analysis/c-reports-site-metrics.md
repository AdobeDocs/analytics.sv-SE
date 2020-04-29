---
description: Visar kvantitativ information om webbplatsen, t.ex. hur många gånger besökarna tittade på vissa sidor, antalet totala inköp från specifika sidor, när de kom och liknande kvantitativa data. Var och en av dessa rapporter är ett mätvärde som du kan placera i andra objektbaserade rapporter.
title: Site Metrics-rapporter
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Site Metrics-rapporter

Visar kvantitativ information om webbplatsen, t.ex. hur många gånger besökarna tittade på vissa sidor, antalet totala inköp från specifika sidor, när de kom och liknande kvantitativa data. Var och en av dessa rapporter är ett mätvärde som du kan placera i andra objektbaserade rapporter.

## Site Metrics-rapporter {#concept_0639CA16551749A693F49ADED4842CCE}

Visar kvantitativ information om webbplatsen, t.ex. hur många gånger besökarna tittade på vissa sidor, antalet totala inköp från specifika sidor, när de kom och liknande kvantitativa data. Var och en av dessa rapporter är ett mätvärde som du kan placera i andra objektbaserade rapporter.

Mätrapporter trendas över tid. Du kan använda tid- och veckodagsgranularitet för dessa rapporter. Alternativt kan du analysera hur lång tid du lagt ned på webbplatsen, inköp, intäkter och liknande.

Följande rapporter om webbplatsstatistik finns på [!UICONTROL Site Metrics] menyn.

## Sidvisningsrapport {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

En trendrapport som visar hur många gånger webbplatsens sidor har visats för den valda tidsperioden (timme, dag, vecka, månad, kvartal eller år). Ett [!UICONTROL Page View] är en begäran om ett helsidesdokument i stället för ett element på en sida, till exempel en bild eller en video. Om en enskild besökare till exempel visar 15 sidor under ett besök räknas 15 sidvisningar. Om en besökare tittar på samma sida tre gånger under ett besök räknas tre sidvisningar. Med den här rapporten kan du spåra sidvyer för varje sida på webbplatsen samt en sammanställning av sidvyer för hela webbplatsen.

## Besöksrapport {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Visar antalet besök som gjorts på hela webbplatsen under en angiven tidsperiod. Ett *besök* är en sekvens av sidvisningar. Ett besök börjar när en besökare läser in en sida och besöket avslutas efter 30 minuters inaktivitet. Ett besök kan pågå flera timmar, så länge besökaren läser in minst en sida före timeout. Ett besök sammanfaller inte nödvändigtvis med en webbläsarsession. Om en besökare till exempel stänger webbläsaren, öppnar webbläsaren igen och kommer till webbplatsen fem minuter senare, känns det som en fortsättning på samma besök. Det innebär också att om en besökare startar på en sida i 35 minuter kommer besöket att ha stängts och bearbetats och ett nytt besök kommer att påbörjas om de klickar till en annan sida. Besök spåras av cookies. Ett besök avbryts efter 12 timmars oavbruten aktivitet.

<!-- 

c_reports_visits.xml

 -->

I marknadsföringsrapporter och analyser kan du köra en [!UICONTROL Visits Report] på en vald sida. Vid ad hoc-analys kan du segmentera data för att visa specifika sidor.

## Unika besökarrapporter {#concept_39097C54E46C496CBAD537329DB3C84A}

En trendrapport som visar hur många unika besökare som har besökt er webbplats. Varje besökare räknas en gång oavsett hur många gånger personen besöker er webbplats. Adobe använder en patentsökt cookie-handskakningsteknik för att skilja en unik besökare från en återkommande besökare. cookie-handskakningen överträffar begränsningarna i webbläsar-cookie-tekniken.

<!-- 

c_reports_unique_visitors.xml

 -->

Du kan använda den här rapporten för att:

* Se hur många olika personer som har visat din webbplats under en viss tidsperiod.
* Se de senaste trafikmönstren och se hur olika kampanjer ger unika besökare på er webbplats.
* Jämför antalet unika besökare med antalet sidvisningar.

## Besökarrapport {#concept_7371DAB5DA474D03A2D1448F151E011B}

Visar antalet unika besökare på webbplatsen för en vald timme, dag, vecka, månad, kvartal eller år. En unik besökare räknas bara en gång för den valda tidsramen. Besökare som återvänder till platsen räknas inte som unika användare igen förrän tidsramen har passerat.

<!-- 

c_reports_visitors.xml

 -->

Det totala värdet som visas längst ned i tabellen är summan av alla besök för den angivna tidsperioden och återspeglar inte alltid antalet unika besökare. Om du till exempel kör en [!UICONTROL Daily Unique Visitors Report] med en tidsram på flera dagar, kan summan innehålla återkommande besökare, eftersom samma besökare kan komma tillbaka nästa dag och räknas om. Om du däremot kör en [!UICONTROL Monthly Unique Visitors Report]sträng återspeglar värdet i kolumnen Summor exakt hur många unika besökare som kom under månaden.

## Tidsåtgång per besök - rapport {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Visar hur lång tid besökarna tillbringar med att visa din webbplats under varje besök. Den har också en genomsnittlig tid på Webbplatsstatistik som visar den genomsnittliga tid som besökare tillbringade med att visa din webbplats.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Använd den här rapporten för att:

* Identifiera hur länge besökarna stannar på er webbplats.
* Identifiera webbplatsinnehåll och kampanjer som väcker besökarnas intresse.
* Ta reda på varför ni har hög trafik, men besökarna ger er av omedelbart.

## Inköpsrapport {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Visar sammanfattningsdata för Intäkter, Beställningar och Enheter. Du kan även visa [!DNL Purchase Conversion Funnel] rapporten.

<!-- 

c_reports_purchases.xml

 -->

* **Intäkter**: Här kan du visa bruttovinster för valda tidsperioder. Exempel på detta är intäkter under mars, inköp förra veckan eller intäkter för idag.
* **Beställningar**: Visar antalet beställningar som gjorts på webbplatsen under den angivna tidsperioden. Beställningar kan innehålla flera produkter.
* **Enheter**: Visar det totala antalet enheter som beställts för den angivna tidsperioden.
* **Inköpskonverteringstratt**: Perfekt för att visa konverteringshändelser på er webbplats om de inträffar i en viss ordning, t.ex. i en butiksinställning. En trattrapport visar konverteringsmåtten för varje steg i konverteringsprocessen samt beställningar, återköp och enheter.

## Kundvagnsrapport {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Visar antalet varukorgar som öppnas under den angivna tidsperioden. Du kan köra rapporter för att analysera kundvagnsvyer, tillägg, borttagningar och utcheckningar. En kundvagn öppnas vanligtvis när en kund väljer en artikel att köpa, men den kan också inträffa utan någon artikel.

<!-- 

c_reports_shopping_cart.xml

 -->

Du kan använda [!UICONTROL Carts Report] till att:

* Bestäm mönster, högsta eller lägsta antal kartor som öppnas på sajten.
* Granska specifika tidsperioder och läs mer om mätvärden som specifikt bidrog till öppnandet av kundvagnen.

## Anpassad händelserapport {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

De konverteringsåtgärder på webbplatsen som du vill att besökarna ska slutföra. Dessa åtgärder kan vara registrering, prenumeration, ifyllnad av leadformulär, chattinitiering, inköp, bokning eller en färdig enkät.

<!-- 

c_reports_custom_events.xml

 -->

Eftersom varje analysrapporteringsserie skiljer sig åt används den här uppsättningen rapporter på olika sätt för varje kund. En [!UICONTROL Custom Event] rapport kan användas som räknare som visar hur många gånger en händelse inträffar. Om **[!UICONTROL event1]** [!UICONTROL Custom Event] till exempel är inställt på att räkna antalet gånger som ett dokument laddas ned, visar rapporten för händelse 1 det totala antalet gånger som händelsen (eller hämtningen) inträffar. Du kan ha flera anpassade händelserapporter.

## Konverteringsrapporter {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Visar intäkter från olika aspekter av webbplatsen. Ni kan se rapporter som visar intäkter från annonskampanjer, intäkter från lojala kunder jämfört med intäkter från nya kunder, en fördelning av intäkter per produkt och många andra intäktsrapporter. Konverteringsrapporter kan även visa andra lyckade händelser som annonsklickningar, nedladdningar eller andra händelser.

<!-- 

c_reports_conversion.xml

 -->

Konverteringsrapportering inkluderar realtidsstatistik över all viktig kundaktivitet, inklusive:

* Kundinköpsmönster
* Kundvagnsstatistik, inklusive utfall
* Kundkonverteringsgrader
* Reklam och kanalpartners effektivitet
* Marknadsföringskampanjer online och offline
* Kundlojalitetsmått
* Insikt i säljcykler

## Marketing Channel-rapporter {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

Marketing Channel-rapporter visar den första och sista beröringen av kanaltilldelningen, med viktiga standardmått som intäkter, order och kostnader, och ni får veta hur mycket intäkter varje kanal genererar. Du konfigurerar kanaldefinitionsregler i [!DNL Admin Console]och API:er som är specifika för kanalrapporterna är tillgängliga.

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL First or Last Touch Channel Report]**: Visar mätvärden som visar data om en viss första-beröringskanal eller sista-beröringskanal. I de här rapporterna kan du dela upp en kanal och visa information om varje kanal. Om AdLens är aktiverat visas klassificeringar i marknadsföringsrapporter och rapporter om analyskanaler.

**[!UICONTROL First or Last Touch Channel Detail Reports]**: Visar detaljer som sidnamn och referenser, som hämtas från kanalvärdena som du anger i [!UICONTROL Set the channel's value to] alternativet när regler konfigureras. Med kanaldetaljrapporter kan du noggrant granska kanaldetaljvärdena från översiktsrapporten.

Mer ingående information om hur du konfigurerar marknadsföringskanalen i marknadsföringsrapporter och analyser finns i hjälpsystemet för [marknadsföringskanaler](/help/components/c-marketing-channels/analyze-mc.md) .
