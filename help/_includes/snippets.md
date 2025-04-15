---
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '2353'
ht-degree: 0%

---
# Fragment

## Äldre Report Builder {#legacy-arb}

>[!IMPORTANT]
>
>Ett nytt och smidigt [Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview) släpptes 16 oktober 2024. Det stöds i Mac, Windows och webbläsare.
>Denna äldre Report Builder-tilläggsversion fungerar fortfarande. Du kan [konvertera dina äldre arbetsböcker](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) till nya Report Builder.

## Rapporter och analyser - meddelande om att produkten har upphört att gälla {#ra-eol}

>[!IMPORTANT]
>
>Från och med den **17 januari 2024** har Adobe upphört med Rapporter och analyser och tillhörande rapporter och funktioner. Vid den tidpunkten slutade rapporter och analyser och alla rapporter och tidsplaner att fungera. Rapporterna, visualiseringarna och den underliggande tekniken som används i rapporter och analyser uppfyller inte längre Adobe teknikstandarder. De flesta funktionerna Rapporter och Analytics är tillgängliga i Analysis Workspace. Mer information finns i [Använda mallar](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Sedan Analysis Workspace lanserades 2015 har funktionerna och funktionerna i Rapporter och analyser flyttats till Analysis Workspace och en tröskel på arbetsflödets paritet har uppnåtts. Det här meddelandet förklarar processen vid slutet av livscykeln.
>
>Läs mer om rapporterna och analysen [Slutet av livscykelmeddelandet](https://www.adobe.com/go/analytics_rnaeol_en).

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Rekommenderas**] | Sorterar komponenter med de som rekommenderas högst upp i listan. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i listan. |
| [!UICONTROL **Alfabetiskt**] | Sorterar komponenterna i bokstavsordning. |
| [!UICONTROL **Kategorisisk**] | Sorterar komponenter efter komponenttyp (dimension, mått, segment, datumintervall). |

{style="table-layout:auto"}

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-releaser finns i [Adobe Analytics-funktionsreleaser](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-releaser finns i [Adobe Analytics-funktionsreleaser](/help/release-notes/releases.md).


## Ansvarsfriskrivning för plugin-program {#plug-in}

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du din organisations Adobe Account Team. De kan ordna ett möte med en konsult för att få hjälp.


## Endast tillgängligt för befintliga kunder {#available-existing-customers}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är bara tillgängliga för befintliga kunder som redan har en licens för funktionen. Funktionen erbjuds inte längre som ett tillägg till befintliga eller nya kunder.
>



## Attributionsmodeller {#attribution-models-details}

En attribueringsmodell avgör vilka dimensionsobjekt som får kredit för ett mätresultat när flera värden visas i en metrisk sökningsfönster. Attributionsmodeller används bara när det finns flera dimensionsobjekt angivna i uppslagsfönstret. Om bara en enda dimensionsobjekt anges får den dimensionsobjektet 100 % kredit oavsett vilken attribueringsmodell som används.

| Ikon | Attributionsmodell | Definition |
| :---: | :--- | --- |
| ![Senaste beröring](/help/assets/icons/AttributeLastTouch.svg) | Senaste beröring | Ger 100 % uppskattning av den beröringspunkt som inträffade senast före konverteringen. Den här attribueringsmodellen är vanligtvis standardvärdet för alla mätvärden där ingen attributmodell har angetts på annat sätt. Organisationer använder vanligtvis den här modellen där tiden för konvertering är ganska kort, till exempel när interna söknyckelord analyseras. |
| ![Första beröring](/help/assets/icons/AttributeFirstTouch.svg) | Första beröring | Ger 100 % kredit till den beröringspunkt som först ses i attribueringssökningsfönstret. Organisationer använder vanligtvis den här modellen för att förstå varumärkesmedvetenhet och kundvärvning. |
| ![Linjär](/help/assets/icons/AttributeLinear.svg) | Linjär | Ger samma beröm till alla kontaktytor som leder till konvertering. Det är användbart när konverteringscyklerna är längre eller kräver mer frekvent kundengagemang. Organisationer använder vanligtvis den här attribueringsmodellen för att mäta hur effektiva mobilappsaviseringar är eller med prenumerationsbaserade produkter. |
| ![Deltagande](/help/assets/icons/AttributeParticipation.svg) | deltagande | Alla unika kontaktpunkter får 100 % beröm. Eftersom varje beröringspunkt får 100 % rabatt läggs måttdata vanligtvis till mer än 100 %. Om en dimensionspost visas flera gånger som leder till en konvertering, dupliceras värdena till 100 %. Den här attribueringsmodellen är perfekt i situationer där du vill förstå vilka kontaktpunkter kunderna exponeras mest för. Medieorganisationer använder vanligtvis den här modellen för att beräkna innehållets hastighet. Butiksorganisationer använder vanligtvis den här modellen för att förstå vilka delar av deras sajt som är avgörande för konverteringen. |
| ![Samma beröring](/help/assets/icons/AttributeSameTouch.svg) | Samma beröring | Ger 100 % kredit till samma händelse som konverteringen inträffade. Om en beröringspunkt inte inträffar för samma händelse som en konvertering, blockeras den under Ingen. Den här attribueringsmodellen är ibland lika med att inte ha någon attribueringsmodell alls. Det är värdefullt i scenarier där du inte vill ha värden från andra händelser som påverkar hur ett mätvärde ger kredit till dimensionsobjekt. Produkt- eller designteam kan använda den här modellen för att utvärdera hur effektiv en sida är där konverteringen sker. |
| ![U-form](/help/assets/icons/AttributeUShaped.svg) | U Shaped | Ger 40 % uppskattning av den första interaktionen, 40 % tack vare den sista interaktionen och delar de återstående 20 % på alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får båda 50 % rabatt. Den här attribueringsmodellen används bäst i scenarier där du värdesätter den första och den sista interaktionen mest, men inte helt vill avvisa ytterligare interaktioner däremellan. |
| ![J-kurva](/help/assets/icons/AttributeJCurve.svg) | J-kurva | Ger 60 % kreativitet till den senaste interaktionen, 20 % tack till den första interaktionen och delar de återstående 20 % på alla kontaktpunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % poäng för den senaste interaktionen och 25 % kredit ges till den första. I likhet med U-Shaped är den här attribueringsmodellen att föredra den första och sista interaktionen, men den är mer prioriterad än den sista interaktionen. |
| ![Omvänd J](/help/assets/icons/AttributeInverseJ.svg) | Inverterad J | Ger 60 % kredit till den första beröringspunkten, 20 % kredit till den sista beröringspunkten och delar de återstående 20 % till alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % kredit för den första interaktionen och 25 % kredit för den sista. I likhet med J-Shaped prioriterar den här attribueringsmodellen den första och sista interaktionen, men prioriterar den första interaktionen mer. |
| ![Tidsminskning](/help/assets/icons/AttributeTimeDecay.svg) | Tidsminskning | Följer en exponentiell minskning med en anpassad halveringsparameter, där standardvärdet är 7 dagar. Vikten för varje kanal beror på hur lång tid det tar mellan öppnandet av kontaktpunkten och den slutliga konverteringen. Formeln som används för att bestämma kredit är `2^(-t/halflife)`, där `t` är tiden mellan en kontaktpunkt och en konvertering. Alla beröringspunkter normaliseras sedan till 100 %. Perfekt för scenarier där du vill mäta attribuering mot en specifik och viktig händelse. Ju längre en konvertering sker efter den här händelsen, desto mindre kredit ges. |
| ![Anpassat](/help/assets/icons/AttributeCustom.svg) | Anpassad | Gör att du kan ange de vikter du vill ge den första beröringspunkten, den sista beröringspunkten och eventuella mellanliggande beröringspunkter. De angivna värdena normaliseras till 100 % även om de anpassade siffrorna inte läggs till i 100. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För interaktioner med två beröringspunkter ignoreras parametern middle. Den första och sista beröringspunkten normaliseras sedan till 100 % och krediteringen tilldelas därefter. Den här modellen är idealisk för analytiker som vill ha fullständig kontroll över sin attribueringsmodell och har särskilda behov som andra attribueringsmodeller inte uppfyller. |
| ![Algoritmisk](/help/assets/icons/AttributeAlgorithmic.svg) | Algoritmisk | Använder statistiska tekniker för att dynamiskt fastställa den optimala kreditfördelningen för det valda måttet. Den algoritm som används för attribuering bygger på Harsanyi Dividend från kooperativ spelteori. Harsanyi-utdelningen är en generalisering av Shapley-värdelösningen (som uppges efter Lloyd Shapley, en Nobel Laureate-ekonom) för att distribuera krediter bland spelarna i ett spel med olika bidrag till resultatet.<br>Vid en hög nivå beräknas attribueringen som en koalition av spelare till vilka ett överskott måste fördelas jämnt. Varje koalitions överskottsfördelning bestäms utifrån det överskott som tidigare skapades genom varje delkoalition (eller tidigare deltagande dimensionsposter) rekursivt. Mer information finns i John Harsanyis och Lloyd Shapley&#39;s original papers:<br>Shapley, Lloyd S. (1953). Ett värde för personliga spel. *Bidrag till spelets teori, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). En förenklad förhandlingsmodell för det personliga kooperativa spelet. *Internationell ekonomisk granskning 4(2)*, 194-220. |

{style="table-layout:auto"}

## Fönstret Tilldelningssökning {#attribution-lookback-window}

Ett uppslagsfönster är den tid som en konvertering bör titta tillbaka för att inkludera beröringspunkter. Om ett dimensionsobjekt anges utanför uppslagsfönstret inkluderas inte värdet i någon attribueringsberäkning.

* **14 dagar**: Kan synkroniseras upp till 14 dagar från när konverteringen gjordes.
* **30 dagar**: Kan synkroniseras upp till 30 dagar från när konverteringen gjordes.
* **60 dagar**: Kan synkroniseras upp till 60 dagar från när konverteringen gjordes.
* **90 dagar**: Återställer upp till 90 dagar från när konverteringen inträffade.
* **Besök**: Går tillbaka till början av besöket där en konvertering inträffade.
* **Besökare (rapportfönster)**: Alla besök kontrolleras fram till den första i månaden i det aktuella datumintervallet. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för besökarens sökning 1 september - 30 september. Om du använder det här uppslagsfönstret kan du ibland se att dimensionsobjekt tilldelas till datum utanför rapportfönstret.
* **Anpassad tid:** Används för att ange ett anpassat uppslagsfönster från när en konvertering inträffade. Du kan ange antalet minuter, timmar, dagar, veckor, månader eller kvartal. Om en konvertering till exempel skedde den 20 februari skulle ett uppslagsfönster på fem dagar utvärdera alla dimensionskontaktytor från den 15 februari till den 20 februari i attribueringsmodellen.

## Attributionsexempel {#attribution-example}

Titta på följande exempel:

1. Den 15 september kommer en person till er webbplats via en betald sökannons, sedan går han/hon iväg.
1. Den 18 september kommer personen till er webbplats igen via en länk för sociala medier som de fått från en vän. De lägger till flera artiklar i kundvagnen, men köper ingenting.
1. Den 24 september skickar marknadsföringsteamet ett e-postmeddelande med en kupong för några av artiklarna i kundvagnen. De använder kupongen, men besöker flera andra sajter för att se om det finns några andra kuponger. De hittar en till genom en displayannons och gör sedan ett köp för 50 dollar.

Beroende på ditt uppslagsfönster och din attribueringsmodell får kanalerna olika krediter. Nedan följer några exempel:

* Med **första beröring** och ett **sessionsfönster** tittar attribueringen bara på det tredje besöket. Mellan e-post och visning var e-post först, så e-post får 100 % rabatt på 50 USD.

* Attribution söker efter alla tre besök med **första beröring** och ett **fönster för personsökning**. Betalsökning var först, så den får 100 % rabatt på 50 USD.

* Med **linjär** och ett **sessionsfönster** delas krediteringen mellan e-post och visning. Båda dessa kanaler får 25 krediter.
Med **linjär** och ett **personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Varje kanal får 12,50 dollar i rabatt för detta inköp.

* Med **J-formad** och ett **personsökningsfönster** delas krediteringen mellan betalsökningar, sociala medier, e-post och visning.

   * 60 % kredit ges för 30 dollar.
   * 20 % kredit ges till betald sökning för 10 dollar.
   * De återstående 20 % är uppdelade i sociala medier och e-post, vilket ger 5 USD till var och en.

* Med **Time Decay** och ett **Personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Använd standardhalveringstiden på 7 dagar:

   * Mellanrum på noll dagar mellan visning och konvertering. `2^(-0/7) = 1`
   * Mellanrum på noll dagar mellan e-postens kontaktpunkt och konvertering. `2^(-0/7) = 1`
   * Ett mellanrum på sex dagar mellan social kontaktyta och konvertering. `2^(-6/7) = 0.552`
   * Mellanrum på nio dagar mellan betald sökningspunkt och konvertering. `2^(-9/7) = 0.41`
   * Normalisering av dessa värden ger följande resultat:

      * Bildskärm: 33,8 %, får 16,88 USD
      * E-post: 33,8 % får 16,88 USD
      * Socialt: 18,6 %, får 9,32 USD
      * Betalsökning: 13,8 %, får 6,92 USD

Konverteringshändelser som vanligtvis har ett heltal delas om kredit tillhör fler än en kanal. Om till exempel två kanaler bidrar till en order med en linjär attribueringsmodell får båda kanalerna 0,5 av den ordningen. Dessa partiella mätvärden summeras för alla personer och avrundas sedan till närmaste heltal för rapportering.

## Jämförelser av resevisualisering {#journey-visualization-comparisons}

Olika visualiseringar i kundreseanalyser är utformade för att analysera de resor du erbjuder dina kunder.

Använd följande information för att välja den visualisering som bäst passar dina behov.

| Funktion | Reseduk | Utfall | Flöde |
|---------|----------|---------|---------|
| **Fördefinierad sidsekvens** | Ja</br>Kombinerar fördefinierad och undersökande analys. Den slutliga sökvägen används när fördefinierade noder används på banan (besökare räknas så länge de till slut går från en fördefinierad nod till en annan). Nästa nod som är direkt (inte slutgiltig) kan också visas. | Ja</br>Sökvägen kan vara en slutlig sökväg eller begränsas till nästa kontaktyta | Nej |
| **Utforska sidsekvenser (ad hoc-analys)** | Ja</br>Kombinerar fördefinierad och undersökande analys. Den slutliga sökvägen används när fördefinierade noder används på banan (besökare räknas så länge de till slut går från en fördefinierad nod till en annan). Nästa nod som är direkt (inte slutgiltig) kan också visas. | Begränsad</br>Du kan högerklicka och visa direkt utfall i en friformstabell. | Ja</br>Endast experimentell analys. Alltid inom en dimensionsinstans mellan noder. Det innebär att varje nod visar den omedelbara (inte slutliga) nästa kontaktyta längs banan. |
| **Visar var personer slutade (föll ut) och fortsatte igenom (gick igenom)** | Ja</br>Visar både fördefinierade och experimentella resor | Ja</br>Visar fördefinierade resor | Ja</br>Visar för experimentella resor |
| **Linjära resor** | Ja | Ja | Nej |
| **Icke-linjära resor med flera startpunkter och sökvägar** | Ja | Nej | Ja |
| **Primärt mått** | Alla mått, inklusive beräknade värden | Endast session eller person | Endast förekomster (banvyer) |
| **Sekundärt mått** | Ja<p>Alla mått, inklusive beräknade värden</p> | Nej | Nej |
| **Komponentstöd i noder eller kontaktytor** | Mätvärden, dimensionsobjekt, filter och datumintervall. | Mätvärden, dimensionsobjekt, filter och datumintervall. | Endast dimensionsobjekt (utom start- och slutkontaktytan) |
| **Jämför filter** | Nej | Ja<p>Jämför två olika filter sida vid sida i samma rapport.</p> | Nej |
| **Komponentinteraktion genom att dra och släppa** | Ja | Ja | Nej |
| **Adobe Journey Optimizer-resor** | Ja</br>Öppna resor från Journey Optimizer för djupgående analyser och anpassningar | Nej | Nej |

{style="table-layout:auto"}
