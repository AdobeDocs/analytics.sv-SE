---
title: Bearbetningsregler för marknadsföringskanaler
description: Bearbetningsreglerna för marknadsföringskanaler avgör om en besökarträff uppfyller kriterierna som tilldelats en kanal. Reglerna bearbetar varje träff en besökare gör på er webbplats. När en regel inte uppfyller villkoren för en kanal, eller om reglerna inte är korrekt konfigurerade, tilldelar systemet träffen Ingen kanal identifierad.
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Bearbetningsregler för marknadsföringskanaler

Bearbetningsreglerna för marknadsföringskanaler avgör om en besökarträff uppfyller kriterierna som tilldelats en kanal. Reglerna bearbetar varje träff en besökare gör på er webbplats. När en regel inte uppfyller villkoren för en kanal, eller om reglerna inte är korrekt konfigurerade, tilldelar systemet träffen Ingen kanal identifierad.

Här följer viktiga riktlinjer för att skapa regler:

* Sortera reglerna i den ordning som du vill att de ska bearbetas.
* Ta med en regel som fångar upp alla, till exempel Annan, i slutet av listan. Den här regeln identifierar extern trafik men inte intern trafik.

   Se [Ingen kanal identifierad.](/help/components/c-marketing-channels/c-faq.md)

> [!NOTE] Även om dessa regler inte påverkar rapportering utanför marknadsföringskanaler påverkar de datainsamlingen för marknadsföringskanaler. Data som samlas in med dessa regler är helt permanenta, och regler som ändras efter det att data har samlats in är inte retroaktiva. Vi rekommenderar att du granskar och tar hänsyn till alla omständigheter innan du sparar, [!UICONTROL Marketing Channel Processing Rules] för att minska risken för att data samlas in i felaktiga kanaler.

## Förutsättningar

* Granska konceptuell information i [Komma igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
* Skapa en eller flera kanaler så att du kan tilldela regler till dem. Se [Lägga till marknadsföringskanaler.](/help/components/c-marketing-channels/c-channels.md)

## Skapa regler för bearbetning av marknadsföringskanal

Skapa regler för bearbetning av marknadsföringskanaler, som avgör om en besökarträff uppfyller kriterierna som tilldelats en kanal.

I den här proceduren används en e-postregel som exempel. Exemplet förutsätter att du har lagt till en e-postkanal i din lista över kanaler på sidan för Marketing Channel Manager.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.

   Om inga kanaler har definierats för rapportsviten visas [!UICONTROL Marketing Channels: Auto Setup] sidan.

   Se [Köra den automatiska installationen](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Stegresultat](assets/marketing_channel_rules.png)

1. Välj på **[!UICONTROL Add New Rule Set]** menyn **[!UICONTROL Email]**.

   Här väljer du inte kanal, utan en mall som fyller i regeln med några av de nödvändiga parametrarna.

   ![Stegresultat](assets/example_email.png)

   Använd boolesk logik (if / then-satser) för att konfigurera en regel. I en regel för e-postkanal kan du till exempel ange inställningar eller information som framhävs i följande regelsats:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   I det här exemplet *`<value>`* är det frågesträngsparametern som du använder för din e-postkampanj, till exempel *`eml`*.
1. Om du vill fortsätta skapa regler klickar du på **[!UICONTROL Add Rule]**.
1. Om du vill prioritera regler drar och släpper du dem till önskad plats.
1. Klicka på **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Vanliga frågor och exempel](/help/components/c-marketing-channels/c-faq.md)


## Regelkriterier för marknadsföringskanal

Den här referenstabellen definierar de fält, alternativ och träffattribut som du kan välja på sidan Bearbetningsregler för marknadsföringskanaler.

| Villkor | Definition |
|--- |--- |
| Alla | Aktiverar endast den här kanalen när alla regler i den numrerade regeln är sanna. |
| Alla | Aktiverar den här kanalen när någon av reglerna i regeluppsättningen är true. Det här alternativet är bara tillgängligt om det finns mer än en regel i den numrerade regeln. |
| AMO-ID | Den primära spårningskod som används av integreringarna i Advertising Cloud och Advertising Analytics. När en av dessa integreringar är aktiverad kan spårningskodprefixet användas för att identifiera Advertising Cloud-specifika kanaler. Använd&quot;AMO ID&quot; börjar med&quot;AL&quot; för sökning,&quot;AC&quot; för visning eller&quot;AO&quot; för sociala medier. När AMO-ID används i marknadsföringskanaler kan värdena för klickning/kostnad/intryck tillskrivas rätt kanal (om de inte är konfigurerade går dessa värden till Direkt eller Ingen). |
| AMO ED ID | Den sekundära spårningskod som används av Advertising Cloud. Huvudsyftet med den här spårningskoden är att den ska fungera som nyckel för att skicka data tillbaka till Ad Cloud. Den kan dock även användas för att identifiera ClickThrottings jämfört med ViewThaves om du vill se dessa som två separata marknadsföringskanaler. Detta kan du göra genom att ställa in marknadsföringskanallogiken för&quot;AMO EF ID&quot; avslutas med &quot;:d&quot; för Display ClickTheves eller&quot;AMO EF ID&quot; slutar med &quot;:i&quot; för DisplayThrotts. Om du inte vill dela upp Visning i två kanaler använder du AMO ID-dimensionen i stället. |
| Konverteringsvariabler | Består av eVars som är aktiverade för den här rapportsviten och gäller bara när dessa variabler ställs in via Adobe-koden på sidan.  Se Implementeringshandboken . |
| Finns | Det finns flera tillgängliga markeringar, bland annat:<ul><li>**Finns** inte: Anger att träffattributet inte finns i begäran. Om användaren till exempel skriver en URL eller klickar på ett bokmärke i en hänvisande domän finns inte det refererande domänattributet.</li><li>**Är tom**: Anger att ett träffattribut finns, vanligtvis en eVar- eller frågesträngsparameter, men det finns inget värde som är associerat med träffattributet.</li><li>**Innehåller** inte: Här kan du till exempel ange att en hänvisande domän inte innehåller ett visst värde (till skillnad från att använda markeringen &quot;Innehåller&quot;).</li></ul> |
| Identifiera kanalen som | Associerar regeln med en marknadsföringskanal som du har lagt till på sidan för Marketing Channel Manager.  Se Lägga till marknadsföringskanaler. |
| Matchar regler för betald sökidentifiering | En betald sökning som identifierats av Adobe. Betalda sökningar är när företag betalar en avgift för sökmotorn för att visa sin webbplats. Betalda sökningar visas vanligtvis högst upp eller till höger i sökresultaten. |
| Matchar reglerna för identifiering av naturlig sökning | En obetald sökning upptäcktes av Adobe. |
| Referenten matchar interna URL-filter | Ett besök vars sid-URL matchar ett internt URL-filter, enligt definition för rapportsviten i Admin Tools. |
| Referenten matchar inte interna URL-filter | Den refererande URL:en matchar inte ett internt URL-filter, som definierats för rapportsviten i Admin Tools. Du kan använda den här inställningen med sidans URL och Exists för att ställa in en regel för att spara alla, så att inga besök hamnar i rapportens avsnitt Ingen kanal identifierad. |
| Ignorera träffar som matchar interna URL-filter | (För referenter) Spårar bara träffar som kommer från externt refererade platser. Vanligtvis låter du den här inställningen vara aktiverad om du inte vill inkludera intern trafik. |
| Är första sidan av besök | Den första sidan av ett besök som Adobe rapporterar. |
| Sida | Sidnamnet på en webbsida på din webbplats som är taggad med Adobes webbfyr. Detta värde motsvarar s.pageName . Exempel är `Home Page` och `About Us`. |
| Siddomän | Domänen för den sida som besökaren hamnar på, t.ex. `products.example.co.uk`. |
| Siddomän och sökväg | Domänen och sökvägen, till exempel `products.example.co.uk/mens/pants/overview.html` . |
| Sidrotdomän (TLD+1) | Rotdomänen för den sida där besökaren pekar, till exempel example.co.uk . |
| Sidans URL | URL-adressen till en webbsida på webbplatsen. |
| Refererande domän | Vilken domän dina besökare kom ifrån innan de besökte din webbplats, till exempel referenter från `abcsite.com` kontra `xyzsite.com`. |
| Frågesträngsparameter | Om en sidadress på webbplatsen ser ut som `https://example.com/?page=12345&cat=1`så är både page och cat frågesträngparametrar. (Se `https://en.wikipedia.org/wiki/Query_string`.)  Du kan bara ange en frågesträngsparameter per regeluppsättning. Om du vill lägga till ytterligare frågesträngsparametrar använder du operatorn och lägger sedan till nya frågesträngsparametrar i regeln. `ANY` |
| Referent | Webbsidans plats (fullständig URL) som besökarna var på innan de kom till webbplatsen. Det finns en referens utanför den definierade domänen. |
| Refererande domän och sökväg | En sammanfogning av den refererande domänen och URL-sökvägen. Exempel:    `www.example.com/products/id/12345` eller `ad.example.com/foo` |
| Refererande parameter | En frågesträngsparameter på referensens URL. Om besökarna till exempel kommer från `example.com/?page=12345&cat=1`är sidan och katten de refererande parametrarna. |
| Refererande rotdomän | Referensens rotdomän. Det finns en referent utanför den definierade domänen. |
| Sökmotor | En sökmotor som Google eller Yahoo! som förde besökare till er webbplats. |
| Sök nyckelord | Ett ord som används för att utföra en sökning med en sökmotor. |
| Sökmotor + nyckelord | En sammanfogning av söknyckelordet och sökmotorn för att unikt identifiera sökmotorn. Om du till exempel söker efter ordet dator identifieras sökmotorn och nyckelordet enligt följande: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Obs!**n = naturlig; p = Betalad |
| Ange kanalens värde till | Förutom att ni vet vilken marknadsföringskanal som för besökaren till er webbplats vet ni vilken banderollannons, söknyckelord eller e-postkampanj i kanalen som får tillgodoräkna er för besökarens webbplatsaktivitet. Detta ID är ett kanalvärde som lagras tillsammans med kanalen. Detta värde är ofta ett kampanj-ID som är inbäddat på landningssidan eller den refererande URL:en. i andra fall är det sökmotorn och nyckelordskombinationen för sökning, eller den refererande URL:en som identifierar besökaren från en viss kanal bäst. |

## Intern kanal (Sessionsuppdatering)

Den interna kanalen (som ofta har bytt namn till Sessionsuppdatering) består av besök på den webbplats där den refererande URL:en matchar inställningen för interna URL-filter i Admin Console, vilket innebär att besökaren kom från webbplatsen för att påbörja sitt besök.

![](assets/int-channel1.png)

### Åsidosätta bästa praxis

Det är bäst att avmarkera alternativet för att åsidosätta sista-beröringen för direktkanaler och interna kanaler så att de inte kan ta åt sig kredit från andra beständiga sista beröringskanaler (eller varandra).

>[!NOTE]Det här dokumentet förutsätter att inställningarna för Åsidosätt inte är markerade för Uppdatera direkt och session.

![](assets/int-channel2.png)

### Åtagandeperiod

Både den första och sista beröringskanalen för en besökare återställs efter 30 dagars inaktivitet i den webbläsaren.

>[!NOTE] 30 dagar är standard och kan ändras efter behov via administratörsinställningarna.

Om besökaren använder webbplatsen ofta följer besökarfönstret med. De måste vara inaktiva i 30 dagar för att perioden ska gå ut och kanalerna ska återställas.
Exempel:

* Dag 1: Användaren kommer till webbplatsen på skärmen. Första och sista-beröringskanalen ställs in på Visning.

* Dag 2: Användaren kommer till webbplatsen för naturlig sökning. Första beröringen är fortfarande Visning och Sista beröringen är inställd på Naturlig sökning.

* Dag 35: Användaren har inte varit på webbplatsen på 33 dagar och återkommer med fliken som han/hon hade öppnat i sin webbläsare. Om man utgår ifrån ett 30-dagars interaktionsfönster skulle fönstret ha stängts och cookies för marknadsföringskanaler skulle ha gått ut. Den första berörings- och den sista beröringskanalen återställs och ställs in på Sessionsuppdatering sedan användaren kom från en intern URL.

### Relation mellan första och sista beröringen

För att förstå interaktionen mellan första och sista beröringen och bekräfta att åsidosättningar fungerar som förväntat kan du ta fram en första beröringskanalrapport, som är underrelaterad till en sista beröringskanalrapport, med nyckelresultatmåttet tillagt i (se exempel nedan). Exemplet visar interaktionen mellan den första och sista beröringskanalen.

![](assets/int-channel3.png)

Skärningen där den första är lika med den sista beröringen markeras med orange. Både Direct- och Session Refresh-uppdatering får bara sista-beröringen om de också var den första beröringskanalen, eftersom de inte kan ta åt sig meriter från andra beständiga kanaler (markerade rader i grått).

### Varför sker sessionsuppdatering?

Eftersom vi vet att uppdatering av senaste sessionen bara kan utföras om det också var den första beröringen förklarar scenarierna nedan hur uppdatering av session kan vara en första beröringskanal.

**Scenario 1: Tidsgräns för session**

En besökare kommer till webbplatsen och lämnar sedan fliken öppen i sin webbläsare för användning vid ett senare tillfälle. Besökarens engagemangsperiod går ut (eller så tar de frivilligt bort sina cookies) och de använder den öppna fliken för att besöka webbplatsen igen. Eftersom den refererande URL:en är en intern domän kommer besöket att klassificeras som Sessionsuppdatering.

**Scenario 2: Alla webbplatssidor är inte taggade**

En besökare kommer till sida A som inte är taggad och går sedan till sida B som är taggad. Sidan A betraktas som den interna referenten och besöket klassificeras som Sessionsuppdatering.

**Scenario 3: Omdirigeringar**

Om en omdirigering inte är inställd för att skicka referensdata till den nya landningssidan, förloras alla data i den verkliga posten, och nu visas omdirigeringssidan (troligtvis en intern sida) som den refererande domänen. Besöken klassificeras som Sessionsuppdatering.

**Scenario 4: Domänövergripande trafik**

En besökare flyttar från en domän som utlöses till Suite A till en andra domän som utlöses till Suite B. Om de interna URL-filtren i Suite B innehåller den första domänen kommer besöket i Suite B att registreras som Internal, eftersom Marketing Channels ser det som ett nytt besök i den andra sviten. Besöken klassificeras som Sessionsuppdatering.

**Scenario 5: Långa inläsningstider**

En besökare hamnar på sida A som har mycket innehåll och Adobe Analytics-koden finns längst ned på sidan. Innan allt innehåll (inklusive bildförfrågan från Adobe Analytics) kan läsas in klickar besökaren på sida B. Sidan B utlöser sin Adobe Analytics-bildförfrågan. Eftersom Page A:s bildförfrågan aldrig har lästs in, visas den andra sidan som den första träffen av besöket i Adobe Analytics, där Sida A är referent. Besöken klassificeras som Sessionsuppdatering.

**Scenario 6: Rensar cookies mitt på webbplatsen**

En besökare kommer till webbplatsen och mitt-session rensar deras cookies. Både första- och sista-beröringskanalen återställs och besöket klassificeras som Sessionsuppdatering (eftersom referenten är intern).
