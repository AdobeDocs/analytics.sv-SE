---
description: Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på vissa webbsidor på webbplatsen. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer efter användaren under en förbestämd tidsperiod.
keywords: eVar
title: Konverteringsvariabler (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 0%

---

# Konverteringsvariabler (eVars)

Custom Insight Conversion Variable (eller eVar) placeras i Adobe-koden på vissa webbsidor på webbplatsen. Dess främsta syfte är att segmentera framgångsstatistik för konverteringar i anpassade marknadsföringsrapporter. En eVar kan vara besöksbaserad och fungera på liknande sätt som cookies. Värden som skickas till eVar-variabler följer efter användaren under en förbestämd tidsperiod.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**

## Konverteringsvariabler (eVars) - översikt

Här följer en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/28759/?quality=12)

När en eVar anges till ett värde för en besökare kommer Adobe automatiskt ihåg det värdet tills det upphör att gälla. Alla lyckade händelser som besökaren påträffar när eVarna är aktiv räknas mot eVarna.

eVars är bäst att använda för att mäta orsak och effekt, till exempel:

* Vilka interna kampanjer som påverkade intäkterna
* Vilka banners som till slut resulterade i en registrering
* Antalet gånger som en intern sökning användes innan en order skapades

Om trafikmätning eller vägning önskas rekommenderas användning av trafikvariabler.

>[!NOTE]
>
>Endast ett värde kan lagras i en eVar i en bildbegäran. Om du vill ha flera värden i ett eVar-värde rekommenderar vi att du implementerar [Listvariabler (listvariabler)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html).

### Konverteringsvariabler - beskrivningar {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Beskrivningar av fält som används när [redigera konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md).

| Element | Beskrivning |
| --- | --- |
| [!UICONTROL Name] | Konverteringsvariabelns egna namn. Det här namnet är det som eVarna refereras till i den allmänna rapporten och kommer att vara namnet på rapporten/dimensionen i den vänstra menyn. |
| [!UICONTROL Type]  (Endast eVar) | Variabelvärdets typ:<ul><li>**[!UICONTROL Text String]**: Hämtar textvärden som används på platsen. Det här är den vanligaste typen av eVar och standardinställningen. Den fungerar på liknande sätt som andra variabler, där värdet i den är en statisk textsträng. Om du spårar saker som interna kampanjer eller interna söknyckelord är det här den rekommenderade inställningen.</li><li>**[!UICONTROL Counter]**: Räknar antalet gånger en åtgärd inträffar före händelsen success. Om du t.ex. använder en eVar för att spåra interna sökningar på webbplatsen anger du det här värdet till [!UICONTROL Text String] för att spåra användningen av söktermer. Ange det här värdet till [!UICONTROL Counter] för att räkna antalet sökningar, oavsett vilka söktermer som används. Du kan t.ex. använda en räknarfunktion för att spåra antalet gånger som någon har använt den interna eVarna innan han eller hon genomför ett köp.</li></ul> |
| [!UICONTROL Allocation] | Avgör hur Analytics tilldelar kredit för en success-händelse om en variabel tar emot flera värden före händelsen. Följande värden stöds:<ul><li>**[!UICONTROL Most Recent]**: Det sista eVarna får alltid medarbetare för framgångshändelser tills eVarna upphör.</li><li>**[!UICONTROL Original Value]**: Den första eVarna får alltid erkännande för lyckade händelser tills eVarna upphör.</li><li>**[!UICONTROL Linear]**: Fördelar lyckade händelser lika i alla eVar. Eftersom linjär allokering endast distribuerar värden inom ett besök bör du använda linjär allokering med en eVar som går ut.</li></ul> **Anteckning**: Om du växlar allokering till eller från Linear visas inte historiska data. Blandning av allokeringstyper i rapporteringsgränssnittet kan leda till feldata i rapporter. En linjär fördelning kan t.ex. dela intäkterna med ett antal olika eVar. När du har ändrat tillbaka till Senaste allokering är 100 % av denna intäkt kopplad till det senaste värdet. Den här associationen kan leda till felaktiga slutsatser från användarna.<br><br>För att undvika risken för förvirring vid rapportering gör Adobe Analytics historiska data otillgängliga för gränssnittet. Den kan visas om du bestämmer dig för att ändra tillbaka den angivna eVarna till den ursprungliga allokeringsinställningen, men du bör inte ändra eVar-allokeringsinställningarna bara för att få tillgång till historiska data. Adobe rekommenderar att du använder en ny eVar när nya allokeringsinställningar är önskade för data som redan registreras, i stället för att ändra allokeringsinställningarna för en eVar som redan har en stor mängd historiska data inbyggda. |
| [!UICONTROL Expire After] | Anger en tidsperiod, eller händelse, efter vilken eVarna förfaller (inte längre får kredit för lyckade händelser). Om en lyckad händelse inträffar efter att eVarna har upphört att gälla, får värdet Ingen kredit för händelsen (ingen eVar var aktiv).  Om du väljer en händelse som ett förfallovärde upphör variabeln bara att gälla om händelsen inträffar. Om händelsen inte inträffar upphör aldrig variabeln att gälla.  De tillgängliga alternativen för förfallodatum kan delas in i fyra huvudkategorier:<ul><li>**På en sidvy eller besöksnivå.** Konverteringshändelser utanför sidvyn eller besöket är inte kopplade till eVarna.</li><li>**Baserat på en tidsperiod, t.ex. dag, vecka, månad eller år.** Konverteringshändelser efter den angivna tidsperioden associeras inte med eVarna. Förfalloperioden börjar när variabeln är inställd. Varorna förfaller beroende på den tid de angavs till den andra (minut, timme, dag, månad osv.): <ul><li>MINUTE=60 sekunder</li><li>HOUR=3600 sekunder (60 minuter)</li><li>DAY=86400 sekunder (24 timmar)</li><li>VECKA=604800 sekunder (7 dagar)</li><li>MONTH=2678400 sekunder (31 dagar)</li><li>QUARTER=8035200 sekunder (93 dagar - 3 månader av 31 dagar)</li><li>YEAR=31536000 sekunder (365 dagar)</li><br>Om ett besök börjar klockan 19.00 måndag och eVarna är klar inom detta besök kl. 19.15, upphör giltighetstiden enligt nedan:<li>Dagen förfaller: eVarna förfaller kl. 19.15 på tisdag.</li><li>Vecka förfaller: eVarna förfaller följande måndag kl. 7:15.</li><li>Månad förfaller: eVarna upphör 31 dagar från måndag 07:15.</li></ul><li>**Särskilda konverteringshändelser.** Andra konverteringshändelser som utlöses efter den specifika händelse som associeras med eVarna.</li><li>**Aldrig.** Så länge cookien för besöks-ID är intakt kan hur lång tid som helst gå mellan eVar och händelse.</li></ul> |
| [!UICONTROL Status]  (Endast eVar) | Definierar [!UICONTROL eVar] status:<ul><li>**Handikappade**: Inaktiverar [!UICONTROL eVar]. Tar bort [!UICONTROL eVar] från listan med konverteringsvariabler.</li><li>**Inga underrelationer**: Hindrar dig från att bryta ned [!UICONTROL eVar] av en dimension.</li><li>**Grundläggande underrelationer**: Du kan dela upp en eVar i en hel dimension (till exempel Produkter eller Campaign).</li></ul> |
| [!UICONTROL Reset] | Återställer alla befintliga värden i eVarna. Använd den här inställningen när du återanvänder en eVar så att du inte blandar ett gammalt värde i en ny rapport. Återställning raderar inte historiska data. |
| [!UICONTROL Merchandising]  (Endast eVar) | Merchandising-variabler kan följa på en av två syntaxer:<ul><li>**[!UICONTROL Products Syntax]**: Associerar eVarna med en produkt. **Anteckning**: If [!UICONTROL Products Syntax] är markerat, [!UICONTROL Merchandising Binding Event] -avsnittet är inaktiverat och kan inte markeras för redigering. För denna syntax [!UICONTROL Binding Events] är inte tillämpliga.</li><li>**[!UICONTROL Conversion Variable Syntax]**: Associerar eVarna med en produkt endast om en [!UICONTROL Binding Event] inträffar. I det här fallet väljer du de händelser som fungerar som [!UICONTROL Binding Events].  Om du ändrar den här inställningen utan att uppdatera JavaScript-koden därefter, kommer förlorade data att uppstå. Se [Marknadsföringsvariabler](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Merchandising Binding Event] (Endast eVar) | Om Merchandising är inställt på [!UICONTROL Conversion Variable Syntax]binder de markerade händelserna det aktuella eVarna med en produkt. Använda en [!UICONTROL Binding Event], ange [!UICONTROL Allocation] till [!UICONTROL Most Recent]. If [!UICONTROL Allocation] är inställd på [!UICONTROL Original Value]den första produktbindningen för eVar återstår tills eVarna går ut. Du kan välja flera händelser genom att hålla ned Ctrl (Windows) eller Cmd (Mac) och klicka på flera objekt i listan. Du kan bara välja en händelse när [!UICONTROL Conversion Variable Syntax] är markerat. |

### Förfallotid

`eVars` förfaller efter en tidsperiod som du anger. När eVarna har gått ut får den inte längre något erkännande för framgångshändelser. eVars kan också konfigureras så att de upphör att gälla vid lyckade händelser. Om du t.ex. har en intern kampanj som upphör efter ett besök, får den interna kampanjen endast kredit för inköp eller registreringar som sker under det besök där de aktiverades.

Det finns två sätt att förfalla en eVar:

* Du kan ange att eVarna ska förfalla efter en angiven tidsperiod eller händelse.
* Du kan använda framtvinga förfallodatum för en eVar genom att återställa den, vilket är användbart när du återanvänder en variabel.

Om du t.ex. ändrar förfallotiden för en eVar från 30 till 90 dagar, kommer insamlade eVar att fortsätta att gälla under den nya förfallotiden (i det här fallet 90 dagar). Systemet tittar bara på den aktuella förfalloinställningen och den sista angivna tidsstämpeln för det eVar-värde som samlats in för att fastställa förfallodatum. Endast **[!UICONTROL Reset]** förfaller värden och gör det omedelbart.

Ett annat exempel: Om en eVar används i maj för att spegla interna kampanjer och upphör efter 21 dagar, och i juni används den för att hämta interna söknyckelord, bör du den 1 juni tvinga fram ett förfallodatum för, eller en återställning av, variabeln. Om du gör det kommer det att bidra till att bevara de interna kampanjvärdena från juni-rapporterna.

### Ärendekänslighet

Variabler är inte skiftlägeskänsliga. Det övre eller nedre fallet som används vid rapportering baseras på det första värdet som serverdelssystemet registrerar. Värdet kan antingen vara den första förekomsten någonsin eller variera med en tidsperiod (t.ex. en månad), beroende på mängden data som är kopplad till rapportsviten.

### Räknare

eVars används oftast för att lagra strängvärden, men de kan också konfigureras för att fungera som räknare. eVars är användbart som räknare när du försöker räkna antalet åtgärder som en användare utför före en händelse. Du kan till exempel använda en eVar för att hämta antalet interna sökningar före köpet. Varje gång en besökare söker bör eVarna innehålla värdet &#39;+1&#39;. Om en besökare söker fyra gånger före ett köp visas en instans för varje totalantal: 1.00, 2.00, 3.00 och 4.00. Endast 4.00 får dock krediter för köphändelsen (beställningar och intäktsstatistik). Endast positiva tal tillåts som värden för en eVar-räknare.

## Lägga till eller redigera konverteringsvariabler

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**.
1. På [!UICONTROL Conversion Variables] klickar du på **[!UICONTROL Expand]** icon [+] bredvid den konverteringsvariabel som du vill ändra.

   eller

   Klicka **[!UICONTROL Add New]** om du vill lägga till en oanvänd eVar i rapportsviten.
1. Markera de konverteringsvariabelfält som du vill ändra.

   Se [Konverteringsvariabler - beskrivningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). I vissa fält kan du skriva direkt i fältet. Med andra kan du välja i en listruta med värden som stöds.
1. Klicka på **[!UICONTROL Save]**.
