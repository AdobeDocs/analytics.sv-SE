---
description: Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på utvalda webbsidor på din webbplats. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer användaren under en förbestämd tidsperiod.
keywords: eVar
title: Konverteringsvariabler (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '1641'
ht-degree: 0%

---

# Konverteringsvariabler (eVars)

Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på utvalda webbsidor på din webbplats. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer användaren under en förbestämd tidsperiod.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**

## Konverteringsvariabler (eVars) - översikt

En videoöversikt över konverteringsvariabler finns i [Introduktion till konverteringsvariabler](https://experienceleague.adobe.com/sv/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) i självstudiehandboken för Analytics.

När en eVar är inställd på ett värde för en besökare kommer Adobe automatiskt ihåg det värdet tills det upphör att gälla. Alla lyckade händelser som besökaren påträffar när eVar-värdet är aktivt räknas mot eVar-värdet.

eVars är bäst att använda för att mäta orsak och effekt, till exempel:

* Vilka interna kampanjer som påverkade intäkterna
* Vilka banners som till slut resulterade i en registrering
* Antalet gånger som en intern sökning användes innan en order skapades

Om trafikmätning eller vägning önskas rekommenderas användning av trafikvariabler.

>[!NOTE]
>
>Endast ett värde kan lagras i en eVar i en bildbegäran. Om du vill ha flera värden i ett eVar-värde rekommenderar vi att du implementerar [listvariabler (listvariabler)](/help/implement/vars/page-vars/page-variables.md).

### Konverteringsvariabler - beskrivningar {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Beskrivningar av fält som används vid [redigering av konverteringsvariabler](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md).

| Element | Beskrivning |
| --- | --- |
| [!UICONTROL Name] | Konverteringsvariabelns egna namn. Detta namn är det som eVar refereras till i den allmänna rapporten och kommer att vara namnet på rapporten/dimensionen i den vänstra menyn. |
| [!UICONTROL Type] (endast eVar) | Variabelvärdets typ:<ul><li>**[!UICONTROL Text String]**: Hämtar textvärden som används på din plats. Det här är den vanligaste typen av eVar och standardinställningen. Den fungerar på liknande sätt som andra variabler, där värdet i den är en statisk textsträng. Om du spårar saker som interna kampanjer eller interna söknyckelord är det här den rekommenderade inställningen.</li><li>**[!UICONTROL Counter]**: Räknar antalet gånger en åtgärd inträffar före händelsen success. Om du till exempel använder en eVar för att spåra interna sökningar på din webbplats anger du det här värdet till [!UICONTROL Text String] för att spåra användningen av söktermer. Ange det här värdet till [!UICONTROL Counter] om du vill räkna antalet sökningar, oavsett vilka söktermer som används. Du kan till exempel använda en eVar-räknare för att spåra hur många gånger någon har använt din interna sökning innan han/hon gör ett köp.</li></ul> |
| [!UICONTROL Allocation] | Avgör hur Analytics tilldelar kredit för en success-händelse om en variabel tar emot flera värden före händelsen. Följande värden stöds:<ul><li>**[!UICONTROL Most Recent]**: Det sista eVar-värdet får alltid erkännande för lyckade händelser tills eVar upphör att gälla.</li><li>**[!UICONTROL Original Value]**: Den första eVar får alltid erkännande för lyckade händelser tills eVar upphör att gälla.</li><li>**[!UICONTROL Linear]**: Allokerar lyckade händelser jämnt över alla eVar-värden. Eftersom linjär allokering endast distribuerar värden inom ett besök bör du använda linjär allokering med ett eVar-förfallodatum för besök.</li></ul> **Obs!**: Genom att växla allokering till eller från Linjär förhindrar du att historiska data visas. Blandning av allokeringstyper i rapporteringsgränssnittet kan leda till feldata i rapporter. En linjär fördelning kan t.ex. dela upp intäkterna i ett antal olika eVar-värden. När du har ändrat tillbaka till Senaste allokering är 100 % av denna intäkt kopplad till det senaste värdet. Den här associationen kan leda till felaktiga slutsatser från användarna.<br><br>För att undvika risken för förvirring vid rapportering gör Adobe Analytics historiska data otillgängliga för gränssnittet. Den kan visas om du bestämmer dig för att ändra tillbaka den angivna eVar-inställningen till den ursprungliga allokeringsinställningen, men du bör inte ändra eVar-allokeringsinställningarna bara för att få tillgång till historiska data. Adobe rekommenderar att du använder en ny eVar när nya allokeringsinställningar efterfrågas för data som redan registreras, i stället för att ändra allokeringsinställningarna för en eVar som redan har en stor mängd historiska data inbyggda. |
| [!UICONTROL Expire After] | Anger en tidsperiod eller händelse efter vilken eVar-värdet förfaller (får inte längre kredit för lyckade händelser). Om en lyckad händelse inträffar efter att eVar förfaller, får värdet Ingen medarbetare för händelsen (ingen eVar var aktiv).  Om du väljer en händelse som ett förfallovärde upphör variabeln bara att gälla om händelsen inträffar. Om händelsen inte inträffar upphör aldrig variabeln att gälla.  De tillgängliga alternativen för förfallodatum kan delas in i fyra huvudkategorier:<ul><li>**På en sidvy eller besöksnivå.** Konverteringshändelser utanför sidvyn eller besöket är inte kopplade till eVar.</li><li>**Baserat på en tidsperiod, till exempel dag, vecka, månad eller år.** Konverteringshändelser efter den angivna tidsperioden associeras inte med eVar. Förfalloperioden börjar när variabeln är inställd. Varorna förfaller beroende på den tid de angavs till den andra (minut, timme, dag, månad osv.): <ul><li>MINUTE=60 sekunder</li><li>HOUR=3600 sekunder (60 minuter)</li><li>DAY=86400 sekunder (24 timmar)</li><li>VECKA=604800 sekunder (7 dagar)</li><li>MONTH=2678400 sekunder (31 dagar)</li><li>QUARTER=8035200 sekunder (93 dagar - 3 månader av 31 dagar)</li><li>YEAR=31536000 sekunder (365 dagar)</li><br>Om ett besök börjar kl. 7:00 måndag och en eVar är klar inom detta besök kl. 7:15 förfaller enligt nedan:<li>Dagens förfallodatum: eVar förfaller klockan :15 på tisdag.</li><li>Vecka förfaller: eVar förfaller följande måndag 07:00.:15</li><li>Månad förfaller: eVar upphör 31 dagar från måndag 07:00.:15</li></ul><li>**Särskilda konverteringshändelser.** Andra konverteringshändelser som utlöses efter den specifika händelse som associeras med eVar.</li><li>**Aldrig.** Så länge som en besökare använder samma identifierare kan all tid passera mellan eVar och händelsen.</li></ul> |
| [!UICONTROL Status] (endast eVar) | Definierar statusen [!UICONTROL eVar]:<ul><li>**Inaktiverad**: Inaktiverar [!UICONTROL eVar]. Tar bort [!UICONTROL eVar] från konverteringsvariabellistan.</li><li>**Inga underrelationer**: Hindrar dig från att dela upp [!UICONTROL eVar] med en dimension.</li><li>**Grundläggande underrelationer**: Gör att du kan dela upp en eVar i en hel dimension (till exempel Produkter eller Campaign).</li></ul> |
| [!UICONTROL Reset] | Återställer alla befintliga värden i eVar. Använd den här inställningen när du återanvänder en eVar så att du inte blandar ett gammalt värde i en ny rapport. Återställning raderar inte historiska data. |
| [!UICONTROL Merchandising] (endast eVar) | Merchandising-variabler kan följa på en av två syntaxer:<ul><li>**[!UICONTROL Products Syntax]**: Associerar eVar-värdet med en produkt. **Obs!**: Om [!UICONTROL Products Syntax] är markerat är [!UICONTROL Merchandising Binding Event]-avsnittet inaktiverat och kan inte markeras för redigering. [!UICONTROL Binding Events] gäller inte för den här syntaxen.</li><li>**[!UICONTROL Conversion Variable Syntax]**: Associerar eVar med en produkt endast om en [!UICONTROL Binding Event] inträffar. I det här fallet väljer du de händelser som fungerar som [!UICONTROL Binding Events].  Om du ändrar den här inställningen utan att uppdatera din JavaScript-kod därefter, kommer data att gå förlorade. Se [Marknadsföring av variabler](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Merchandising Binding Event] (endast eVar) | Om Merchandising är inställt på [!UICONTROL Conversion Variable Syntax] binder de markerade händelserna det aktuella eVar-värdet med en produkt. Om du vill använda en [!UICONTROL Binding Event] anger du [!UICONTROL Allocation] till [!UICONTROL Most Recent]. Om [!UICONTROL Allocation] är inställt på [!UICONTROL Original Value], återstår den första eVar-produktbindningen tills eVar upphör att gälla. Du kan välja flera händelser genom att hålla ned Ctrl (Windows) eller Cmd (Mac) och klicka på flera objekt i listan. Du kan bara välja en händelse när [!UICONTROL Conversion Variable Syntax] är markerat. |

### Förfallotid

`eVars` förfaller efter en tidsperiod som du anger. När eVar upphör får det inte längre någon uppskattning för framgångshändelser. eVars kan också konfigureras så att de upphör att gälla vid lyckade händelser. Om du t.ex. har en intern kampanj som upphör efter ett besök, får den interna kampanjen endast kredit för inköp eller registreringar som sker under det besök där de aktiverades.

Det finns två sätt att förfalla en eVar:

* Du kan ange att eVar ska förfalla efter en angiven tidsperiod eller händelse.
* Du kan använda framtvinga förfallodatum för en eVar genom att återställa den, vilket är användbart när du återanvänder en variabel.

Om du t.ex. ändrar förfallotiden för en eVar från 30 till 90 dagar, kommer de insamlade eVar-värdena att fortsätta att gälla under den nya förfallotiden (i det här fallet 90 dagar). Systemet tittar bara på den aktuella förfalloinställningen och den senaste tidsstämpeln för det eVar-värde som samlats in för att fastställa förfallodatum. Endast alternativet **[!UICONTROL Reset]** förfaller värden och gör det omedelbart.

Ett annat exempel: Om en eVar används i maj för att spegla interna kampanjer och upphör efter 21 dagar, och i juni används den för att hämta interna söknyckelord, bör du den 1 juni tvinga fram en förfallotid för, eller återställning av, variabeln. Om du gör det kommer det att bidra till att bevara de interna kampanjvärdena från juni-rapporterna.

### Ärendekänslighet

Variabler är inte skiftlägeskänsliga. Det övre eller nedre fallet som används vid rapportering baseras på det första värdet som serverdelssystemet registrerar. Värdet kan antingen vara den första förekomsten någonsin eller variera med en tidsperiod (t.ex. en månad), beroende på mängden data som är kopplad till rapportsviten.

### Räknare

eVars används oftast för att lagra strängvärden, men de kan också konfigureras för att fungera som räknare. eVars är användbart som räknare när du försöker räkna antalet åtgärder som en användare utför före en händelse. Du kan t.ex. använda en eVar för att hämta in antalet interna sökningar före köpet. Varje gång en besökare söker bör eVar innehålla värdet &#39;+1&#39;. Om en besökare söker fyra gånger före ett köp visas en instans för varje totalantal: 1.00, 2.00, 3.00 och 4.00. Endast 4.00 får dock krediter för köphändelsen (beställningar och intäktsstatistik). Endast positiva tal tillåts som värden för en eVar-räknare.

## Lägga till eller redigera konverteringsvariabler

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**.
1. På sidan [!UICONTROL Conversion Variables] klickar du på ikonen **[!UICONTROL Expand]** [+] bredvid den konverteringsvariabel som du vill ändra.

   eller

   Klicka på **[!UICONTROL Add New]** om du vill lägga till en oanvänd eVar i rapportsviten.
1. Markera de konverteringsvariabelfält som du vill ändra.

   Se [Konverteringsvariabler - beskrivningar](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). I vissa fält kan du skriva direkt i fältet. Med andra kan du välja i en listruta med värden som stöds.
1. Klicka på **[!UICONTROL Save]**.
