---
description: Sekventiella segment skapas med operatorn THEN i stället för AND eller OR. DÄREFTER betyder det att ett segmentvillkor är uppfyllt, följt av ett annat. Som standard identifierar ett sekventiellt segment alla matchande data och visar filtret Inkludera alla. Sekventiella segment kan filtreras ytterligare till en delmängd av matchande träffar med alternativen Endast före sekvens och Endast efter sekvens.
title: Skapa sekventiella segment
feature: Segmentation
exl-id: 2ac4e6db-3111-45e5-bedf-7d9b7b1ae352
source-git-commit: 55c5e6fb790cf9fa49304e8a766f982bccf346b6
workflow-type: tm+mt
source-wordcount: '3658'
ht-degree: 1%

---

# Skapa sekventiella segment

Sekventiella segment skapas med operatorn THEN i stället för AND eller OR. DÄREFTER betyder det att ett segmentvillkor är uppfyllt, följt av ett annat. Som standard identifierar ett sekventiellt segment alla matchande data och visar filtret Inkludera alla. Sekventiella segment kan filtreras ytterligare till en delmängd av matchande träffar med alternativen Endast före sekvens och Endast efter sekvens.

![](assets/before-after-sequence.png)

Dessutom kan du begränsa sekventiella segment till en viss tidslängd, granularitet och antal mellan kontrollpunkterna med hjälp av [Efter- och Inom-operatorer](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Här är en video om sekventiell segmentering:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Inkludera alla {#section_75ADDD5D41F04800A09E592BB2940B35}

När du skapar ett segment där Inkludera alla är angivet identifierar segmentet banor som matchar det angivna mönstret som helhet. Detta är ett exempel på ett grundläggande sekvenssegment som söker efter en träff (sida A) följt av en annan (sida B) som besökts av samma besökare. Segmentet är inställt på Inkludera alla.

![](assets/sequence-filter.png)

| Om resultatet.. | Sekvens |
|--- |--- |
| Matchar | A och sedan B<br>A sedan (vid ett annat besök) B<br>A och sedan D och sedan B |
| Matchar inte | B och A |

## Endast före sekvens och Endast efter sekvens {#section_736E255C8CFF43C2A2CAAA6D312ED574}

Alternativen **[!UICONTROL Only Before Sequence]** och **[!UICONTROL Only After Sequence]** filtrera segmentet till en delmängd av data före eller efter den angivna sekvensen.

* **Endast före sekvens**: Innehåller alla träffar före en sekvens + den första träffen i själva sekvensen (se exempel 1, 3). Om en sekvens visas flera gånger i en bana innehåller&quot;Endast före sekvens&quot; den första träffen av den sista sekvensen i sekvensen och alla tidigare träffar (se exempel 2).
* **Endast efter sekvens**: Innehåller alla träffar efter en sekvens + den sista träffen i själva sekvensen (se exempel 1, 3). Om en sekvens visas flera gånger i en bana innehåller&quot;Endast efter&quot; den senaste träffen av den första sekvensen och alla efterföljande träffar (se exempel 2).

Ta till exempel en sekvens av B -> D. De tre filtren identifierar träffar på följande sätt:

**Exempel 1: B och D visas en gång**

| Exempel | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Inkludera alla | A | B | C | D | E | F |
| Endast före sekvens | A | B |  |  |  |  |
| Endast efter sekvens |  |  |  | D | E | F |

**Exempel 2: B och D visas flera gånger**

| Exempel | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Inkludera alla | A | B | C | D | B | C | D | E |
| Endast före sekvens | A | B | C | D | B |  |  |  |
| Endast efter sekvens |  |  |  | D | B | C | D | E |

Låt oss även sätta ihop konceptet med djupdimensionen.

**Exempel 3: Träff Djup 3 och 5**

![](assets/hit-depth.png)

## Begränsningar för Dimension {#section_EAFD755F8E674F32BCE9B642F7F909DB}

I en&quot;inom&quot;-sats mellan THEN-programsatser kan du lägga till, till exempel,&quot;inom 1 nyckelordsinstans för sökning&quot;,&quot;inom 1 instans av eVar 47&quot;. Detta begränsar segmentet till en instans av en dimension.

Om du ställer in en Within Dimension-sats mellan regler kan ett segment begränsa data till sekvenser där den satsen uppfylls. Se exemplet nedan, där begränsningen är inställd på &quot;Inom 1 sida&quot;:

![](assets/sequence-filter4.png)

| Om resultatet.. | Sekvens |
|--- |--- |
| Matchar | A och sedan B |
| Matchar inte | A sedan C och B (eftersom B inte var inom 1 sida av A)<br>**Obs!**  Om dimensionsbegränsningen tas bort kommer både&quot;A, B&quot; och&quot;A, sedan C, B&quot; att matcha. |

## Enkel sidvisningssekvens

Identifiera besökare som visade en sida och sedan visade en annan sida. Data på träffnivå filtrerar den här sekvensen oavsett tidigare, tidigare eller tillfälliga besökssessioner eller tidpunkten eller antalet sidvisningar som inträffar mellan.

**Exempel**: Besökaren visade sida A och visade sedan sida B i samma eller ett annat besök.

**Användningsexempel**

Här följer några exempel på hur segmentet kan användas.

1. Besökarna på en sportsajt kan se landningssidan för fotboll och sedan se landningssidan för basketboll i sekventiell ordning, men inte nödvändigtvis på samma besök. Detta får en kampanj för att göra basketinnehåll till fotbollstittare under fotbollssäsongen.
1. Bilhandlarna ser en relation mellan dem som landar på kundlojalitetssidan och sedan går till videon när som helst under besöket eller vid ett annat besök.

**Skapa det här segmentet**

Du kapslar in två sidlinjaler i en översta nivå [!UICONTROL Visitor] behållare och sekvens av sidträffar med [!UICONTROL THEN] -operator.

![](assets/segment_sequential_1.png)

## Besökssekvens mellan besök

Identifiera de besökare som föll ned från en kampanj men sedan återvände till sekvensen av sidvisningar i en annan session.

**Exempel**: Besökaren visade sida A vid ett besök och visade sedan sida B vid ett annat besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökarna på Sports-sidan på en nyhetsplats går sedan igenom Sports-sidan i en annan session.
* En klädhandlare ser en relation mellan besökare som landar på en landningssida under en session och sedan går direkt till utcheckningssidan under en annan session.

**Skapa det här segmentet**

Det här exemplet kapslar två **[!UICONTROL Visit]** behållare på den översta nivån **[!UICONTROL Visitor]** behållare och sekventierar segmentet med [!UICONTROL THEN] -operator.

![](assets/visitor_seq_across_visits.png)

## Sekvens på blandnivå

Identifiera besökare som tittar på två sidor över ett obestämt antal besök, men sedan visa en tredje sida vid ett separat besök.

**Exempel**: Besökarna besöker sida A och sedan sida B i ett eller flera besök, följt av ett besök på sida C i ett separat besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökarna besöker först en nyhetssajt och ser sedan sportsidan i samma besök. På ett annat besök besöker besökaren vädersidan.
* Återförsäljaren definierar besökare som går in på huvudsidan och sedan går till sidan Mitt konto. De besöker även sidan Visa kundvagn.

**Skapa det här segmentet**

1. Släpp två siddimensioner från de vänstra rutorna på den översta nivån [!UICONTROL Visitor] behållare.
1. Lägg till operatorn THEN mellan dem.
1. Klicka **[!UICONTROL Options]** > **[!UICONTROL Add container]** och lägga till en [!UICONTROL Visit] behållare under [!UICONTROL Visitor] nivå och sekvens med [!UICONTROL THEN] -operator.

![](assets/mixed_level_checkpoints.png)

## Sammanställningsbehållare

Lägga till flera [!UICONTROL Hit] behållare i en [!UICONTROL Visitor] Med behållare kan du använda lämpliga operatorer mellan samma typ av behållare och använda regler och dimensioner som Sida och Besöksnummer för att definiera sidvyn och ange en sekvensdimension i [!UICONTROL Hit] behållare. Genom att lägga på logik på träffnivå kan du begränsa och kombinera matchningar på samma träffnivå i [!UICONTROL Visitor] behållare för att skapa en rad olika segmenttyper.

**Exempel**: Besökarna besökte sida A efter den första träffen i sidvysekvensen (sida D i exemplet) och besökte sedan antingen sida B eller sida C utan hänsyn till antalet besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Identifiera besökare som går till huvudlandningssidan på ett besök, och se sedan sidan med kläder för män på ett annat besök, och titta sedan på antingen Womans eller Children&#39;s landningssida vid ett annat besök.
* Ett e-zine fångar de besökare som går till hemsidan vid ett besök, på en annan sajt och på en annan besökssida.

**Skapa det här segmentet**

1. Välj [!UICONTROL Visitor] som behållare på den översta nivån.
1. Lägg till två [!UICONTROL Hit]behållare på -nivå - en dimension med en lämplig numerisk dimension sammanfogad på samma [!UICONTROL Hit] nivå efter [!UICONTROL AND] och [!UICONTROL OR] -operator.
1. I [!UICONTROL Visit] behållare, lägg till ytterligare [!UICONTROL Hit] container and nset two additional [!UICONTROL Hit] behållare som har anslutits till en [!UICONTROL OR] eller [!UICONTROL AND] -operator.

   Sekvens för dessa kapslade [!UICONTROL Hit] behållare med [!UICONTROL THEN] -operator.

![](assets/aggregate_checkpoints2.png)

## &quot;Kapsling&quot; i sekventiella segment

Genom att placera kontrollpunkter vid båda [!UICONTROL Visit] och [!UICONTROL Hit] kan du begränsa att segmentet uppfyller kraven inom ett visst besök eller en viss träff.

**Exempel**: Besökaren besökte sida A och besökte sedan sida B under samma besök. Vid ett nytt besök gick besökaren till sida C.

**Skapa det här segmentet**

1. Under en översta nivå [!UICONTROL Visit] container, drag in two page dimensions.
1. Markera båda reglerna flera gånger, klicka **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]** och ändra det till [!UICONTROL Visit] behållare.
1. Förena dem med en [!UICONTROL THEN] -operator.
1. Skapa en Träff-behållare som en peer till [!UICONTROL Visit] behållare och dra i en siddimension.
1. Förena den kapslade sekvensen i [!UICONTROL Visit] behållare med [!UICONTROL Hit] behållare som använder en annan [!UICONTROL THEN] -operator.

![](assets/nesting_sequential_seg.png)

## Exkludera träffar

Segmentregler inkluderar alla data såvida du inte uttryckligen exkluderar [!UICONTROL Visitor], [!UICONTROL Visit], eller [!UICONTROL Hit] data med [!UICONTROL Exclude] regel. Det gör att ni kan avfärda vanliga data och skapa segment med mer fokus. Eller så kan du skapa segment som utesluter hittade grupper för att identifiera den återstående datauppsättningen, till exempel skapa en regel som innefattar framgångsrika besökare som lade order och sedan exkludera dem för att identifiera&quot;icke-köpare&quot;. I de flesta fall är det dock bättre att skapa regler som utesluter breda värden i stället för att använda [!UICONTROL Exclude] regel för att ange specifika inkluderingsvärden som mål.

Exempel:

* **Uteslut sidor**. Använd en segmentregel för att ta bort en viss sida (t.ex. *`Home Page`*) från en rapport skapar du en träff-regel där sidan är lika med&quot;Hemsida&quot; och utesluter den sedan. Den här regeln inkluderar automatiskt alla värden förutom hemsidan.
* **Uteslut refererande domäner**. Använd en regel som endast inkluderar refererande domäner från Google.com och utesluter alla andra.
* **Identifiera icke-köpare**. Identifiera när order är större än noll och exkludera sedan [!UICONTROL Visitor].

The [!UICONTROL Exclude] -operatorn kan användas för att identifiera en sekvens där specifika besök eller träffar inte utförs av besökaren. [!UICONTROL Exclude Checkpoints] kan även ingå i en [Logikgrupp](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

### Uteslut mellan kontrollpunkter

Använd logik för att segmentera besökare där en kontrollpunkt inte uttryckligen förekommer mellan två andra kontrollpunkter.

**Exempel**: Besökare som besökt sida A och sedan besökt sida C - men som inte besökt sida B.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökare på en livsstilssida och sedan på Theatre utan att gå till Arts-sidan.
* En bilhandlare ser en relation mellan dem som besöker landningssidan och sedan går direkt till kampanjen&quot;Inget intresse&quot; utan att gå till sidan&quot;Fordon&quot;.

**Skapa det här segmentet**

Skapa ett segment på samma sätt som för ett enkelt, blandat eller kapslat sekventiellt segment och ange sedan [!UICONTROL EXCLUDE] operatorn för behållarelementet. Exemplet nedan är ett sammanställningssegment där de tre [!UICONTROL Hit] behållarna dras till arbetsytan, [!UICONTROL THEN] -operatorn som är tilldelad att gå med i behållarlogiken, utelämnar sedan den mellersta sidvisningsbehållaren så att endast besökare som gick från sidan A till sidan C tas med i sekvensen.

![](assets/exclude_between_checkpoints.png)

### Uteslut i början av sekvensen

Om kontrollpunkten för uteslutning är i början av ett sekventiellt segment ser den till att en utesluten sidvy inte inträffade före den första icke-uteslutna träffen.

En restaurang vill t.ex. se invettera användare som undviker huvudlandningssidan och gå direkt till sidan Beställ ut. Det här exemplet kan förenklas för en besökare som vill undvika att besöka sida A och gå direkt till sida B.

**Skapa det här segmentet**

Skapa två separata träff-behållare i en besöksbehållare på den översta nivån. Ange sedan [!UICONTROL EXCLUDE] -operator för den första behållaren.

![](assets/exclude_beginning_sequence.png)

### Uteslut vid sekvensslut

Om den utelämnade kontrollpunkten finns i slutet av en sekvens ser det till att kontrollpunkten inte inträffade mellan den sista icke-utelämnade kontrollpunkten och slutet av besökarsekvensen.

En klädbutik vill till exempel se alla besökare som tittade på en produktsida men aldrig besökt sin kundvagn efteråt. Det här exemplet kan förenklas för en besökare som går till sida A och sedan aldrig kommer till sida B vid aktuella eller efterföljande besök.

**Skapa det här segmentet**

Skapa ett enkelt sekvenssegment genom att dra två [!UICONTROL Hit] behållare till arbetsytan och ansluta dem med [!UICONTROL THEN] -operator. Tilldela sedan [!UICONTROL EXCLUDE] operatorn till den andra [!UICONTROL Hit] -behållare i sekvensen.

![](assets/exclude_end_sequence.png)

## Behållare för logikgrupp

Behållare för logikgrupp krävs för att gruppera villkor i en enda kontrollpunkt för sekventiellt segment. Den speciella logikgruppsbehållaren är endast tillgänglig i sekventiell segmentering för att säkerställa att villkoren uppfylls efter en sekventiell kontrollpunkt och före efterföljande kontrollpunkter. Villkoren i Logic Group-kontrollpunkten kan uppfyllas i vilken ordning som helst. Icke-sekventiella behållare (träff, besök, besökare) kräver däremot inte att deras villkor uppfylls i den övergripande sekvensen, vilket ger ointuitiva resultat om de används med en THEN-operator.
The [!UICONTROL Logic Group] behållaren är utformad för att behandla *flera kontrollpunkter som en grupp*, *utan någon beställning* bland de grupperade kontrollpunkterna. Med andra ord, vi bryr oss inte om ordningen på kontrollpunkterna i den gruppen. Du kan till exempel inte kapsla en [!UICONTROL Visitor] behållare i en [!UICONTROL Visitor] behållare. I stället kan du kapsla en [!UICONTROL Logic Group] behållare i en [!UICONTROL Visitor] behållare med specifik [!UICONTROL Visit]-level och [!UICONTROL Hit]kontrollpunkter på -nivå.

>[!NOTE]
>
>A [!UICONTROL Logic Group] kan bara definieras i ett sekventiellt segment, vilket innebär att [!UICONTROL THEN] -operatorn används i uttrycket.

| Behållarhierarki | Illustration | Definition |
|---|---|---|
| Standardbehållarhierarki | ![](assets/nesting_container.png) | I [!UICONTROL Visitor] behållare, [!UICONTROL Visit] och [!UICONTROL Hit] behållarna kapslas in sekventiellt för att extrahera segment baserat på träffar, antalet besök och besökaren. |
| Logikbehållarhierarki | ![](assets/logic_group_hierarchy.png) | Standardbehållarhierarkin krävs även utanför [!UICONTROL Logic Group] behållare. Men i [!UICONTROL Logic Group] -behållaren kräver inte kontrollpunkterna någon etablerad ordning eller hierarki. Dessa kontrollpunkter behöver bara uppfyllas av besökaren i valfri ordning. |

Logikgrupper kan verka skrämmande - här följer några tips om hur du använder dem:

**Logic Group eller Hit/Visit container?**
Om du vill gruppera sekventiella kontrollpunkter är din&quot;behållare&quot; logikgrupp. Om dessa sekventiella kontrollpunkter måste finnas inom ett enda träffs- eller besöksomfång, krävs dock en träff- eller besöksbehållare. (En träff passar förstås inte för en grupp av sekventiella kontrollpunkter, när en träff inte kan kreditera mer än en kontrollpunkt).

**Förenklar logikgrupper skapandet av sekventiella segment?**
Ja, det kan de. Låt oss anta att du försöker identifiera det här segmentet av besökare: **Besökare som visade sida A visade sedan sidorna i B, C och D**

Du kan skapa det här segmentet utan en logikgruppsbehållare, men det är komplicerat och mödosamt. Du måste ange varje sidsekvens som besökaren kan visa:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

En logikgruppsbehållare förenklar byggandet av det här segmentet avsevärt, vilket visas här:

![](assets/logic-grp-example.png)


### Bygg ett logikgruppssegment {#section_A5DDC96E72194668AA91BBD89E575D2E}

Precis som andra behållare, [!UICONTROL Logic Group] behållare kan byggas på flera sätt i [!UICONTROL Segment Builder]. Här är det bästa sättet att kapsla [!UICONTROL Logic Group] behållare:

1. Dra mått, händelser eller segment från de vänstra rutorna.
1. Ändra den övre behållaren till en [!UICONTROL Visitor] behållare.
1. Ändra [!UICONTROL AND] eller [!UICONTROL OR] -operatorn infogad som standard till THEN-operatorn.
1. Välj [!UICONTROL Hit] behållare (Dimension, händelse eller objekt) och klicka på **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**.
1. Klicka på behållarikonen och välj **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. Nu kan du ange [!UICONTROL Hit] inom [!UICONTROL Logic Group] behållare utan hänsyn till hierarkin.

### Kontrollpunkter för logikgrupp i vilken ordning som helst

Använda [!UICONTROL Logic Group] gör att du kan uppfylla villkor i den gruppen som ligger utanför sekvensen. På så sätt kan du skapa segment där [!UICONTROL Visit] eller [!UICONTROL Hit] behållaren inträffar oavsett den normala hierarkin.

**Exempel**: Besökare som besökt sida A, besökte sedan sida B och sida C i valfri ordning.

**Skapa det här segmentet**

Sidan B och C är kapslade i en [!UICONTROL Logic Group] behållaren innanför [!UICONTROL Visitor] behållare. The [!UICONTROL Hit] behållaren för A följs sedan av [!UICONTROL Logic Group] behållare med B och C identifierade med [!UICONTROL AND] -operator. För att det finns i [!UICONTROL Logic Group], är sekvensen inte definierad och om du trycker på båda sidorna B och C i någon ordning blir argumentet true.

![](assets/logic_group_any_order2.png)

**Ett exempel**: Besökare som besökt sida B eller sida C och sedan besökt sida A:

![](assets/logic_group_any_order3.png)

Segmentet måste matcha minst en av logikgruppens kontrollpunkter (B eller C). Logikgruppsvillkor kan även uppfyllas i samma träff eller över flera träffar. &#x200B;

### Logggruppsmatchning

Använda [!UICONTROL Logic Group] gör att du kan uppfylla villkor i den gruppen som ligger utanför sekvensen. I det här osorterade första matchningssegmentet [!UICONTROL Logic Group] först identifieras regler som antingen en sidvy av sida B eller sida C och därefter som en vy av sida A.

**Exempel**: Besökare som besökt antingen sida B eller sida C, besökte sedan sida A.

**Skapa det här segmentet**

Dimensionerna för sida B och sida C är grupperade i en [!UICONTROL Logic Group] behållare med [!UICONTROL OR] -operatorn markerad och sedan [!UICONTROL Hit]behållare som identifierar en sidvy av sida A som värde.

![](assets/logic_group_1st_match.png)

### Logikgrupp exkluderar OCH

Skapa segment med [!UICONTROL Logic Group] där flera sidvyer har sammanställts för att definiera vilka sidor som behöver fyllas medan andra sidor specifikt missade. ****

**Exempel**: Besökaren besökte sida A och besöker sedan uttryckligen inte sida B eller C, utan träffsida D.

**Skapa det här segmentet**

Bygg segmentet genom att dra Dimensioner, händelser och färdiga segment från den vänstra panelen. Se [Bygga ett logikgruppssegment](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Efter kapsling av värdena i [!UICONTROL Logic Group]klickar du på **[!UICONTROL Exclude]** i [!UICONTROL Logic Group] behållare.

![](assets/logic_exclude_and.png)

### Logikgrupp exkluderad ELLER

Skapa segment med [!UICONTROL Logic Group] där flera sidvyer har sammanställts för att definiera vilka sidor som behöver fyllas medan andra sidor specifikt missade.

**Exempel**: Besökare som besökt sida A, men inte besökt sida B eller sida C före sida A.

**Skapa det här segmentet**

De inledande B- och C-sidorna identifieras i en [!UICONTROL Logic Group] behållare som är exkluderad och därefter en träff till sida A av besökaren.

Bygg segmentet genom att dra Dimensioner, händelser och färdiga segment från den vänstra panelen.

Efter kapsling av värdena i [!UICONTROL Logic Group]klickar du på **[!UICONTROL Exclude]** i [!UICONTROL Logic Group] behållare.

![](assets/logic_exclude_or.png)

## Bygg tidsbesparande och tidsbesparande segment

Använd [!UICONTROL Within] och [!UICONTROL After] -operatorer inbyggda i huvudet för varje behållare för att definiera tid, händelser och antal.

![](assets/then_within_operators.png)

Du kan begränsa matchningen till en viss tidsperiod med hjälp av [!UICONTROL Within] och [!UICONTROL After] behållare och specificera granularitet och antal. The [!UICONTROL Within] -operatorn används för att ange en maxgräns för hur lång tid det tar mellan två kontrollpunkter. The [!UICONTROL After] -operatorn används för att ange en minimigräns för hur lång tid det tar mellan två kontrollpunkter.

### Efter och inom operatorer {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

Längden anges med en versal som representerar granulariteten följt av en siffra som representerar repetitionsantalet för granulariteten.

**[!UICONTROL Within]** innehåller slutpunkten (mindre än eller lika med).

**[!UICONTROL After]** innehåller inte slutpunkten (större än).

| Operatorer | Beskrivning |
|--- |--- |
| EFTER | Operatorn Efter används för att ange en minimigräns för hur lång tid det tar mellan två kontrollpunkter. När du anger After-värdena börjar tidsgränsen när segmentet används. Om till exempel operatorn Efter är inställd på en behållare för att identifiera besökare som besöker sida A men inte återvänder till sida B förrän efter en dag, börjar den dagen när besökaren lämnar sida A. För att besökaren ska kunna inkluderas i segmentet måste minst 1440 minuter (en dag) visas efter att sidan A har lämnat sidan till sidan B. |
| INOM | Operatorn Inom används för att ange en maximal tidsgräns mellan två kontrollpunkter. Om till exempel operatorn Inom är inställd på en behållare för att identifiera besökare som besöker sida A och sedan återgår till sida B inom en dag, börjar den dagen när besökaren lämnar sida A. För att inkluderas i segmentet får besökaren högst en dag innan sidan B öppnas. För att besökaren ska kunna delta i segmentet måste besöket på sida B äga rum inom högst 1440 minuter (en dag) efter att sidan A har lämnat sidan B. |
| EFTER/INOM | När du använder operatorerna Efter och Inom är det viktigt att du förstår att båda operatorerna börjar och slutar parallellt, inte sekventiellt.   Om du till exempel skapar ett segment med behållaren inställd på:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Villkoren för att identifiera besökare i segmentet är bara uppfyllda mellan 1 och 2 veckor. Båda villkoren tillämpas från och med den första sidträffen. |

### Använda operatorn Efter

* Med Tid efter kan du spåra efter år, månad, dag, timme och minut för att matcha besöken.
* Tid efter kan bara användas på en [!UICONTROL Hit] eftersom det är den enda nivån för vilken en sådan fin granularitet har definierats.

**Exempel**: Besökare som besökt sida A besökte sedan sida B först efter 2 veckor.***

![](assets/time_between_after_operator.png)

**Skapa segmentet**: Det här segmentet skapas genom att du lägger till en [!UICONTROL Visitor] behållare med två [!UICONTROL Hit] behållare. Du kan sedan ange [!UICONTROL THEN] och öppna [!UICONTROL AFTER] nedrullningsbar lista och ange antalet veckor.

![](assets/after_operator.png)

**Matchar**

Om en träff på sida A inträffar den 1 juni 2019, kl. 00:01, kommer följande träff på sida B att matchas så länge som det kommer före den 15 juni 2019 kl. 00:01 (14 dagar senare).

| Tryck på A | Träff B | Matchande |
|--- |--- |--- |
| **A** hit: 1 juni 2019 00:01 | **B** hit: 15 juni 2019 00:01 | **Matchar:** Tidsbegränsningen matchar eftersom den är efter 1 juni 2019 (två veckor). |
| **A** hit: 1 juni 2019 00:01 | **B** hit: 8 juni 2019 kl. 00:01 15 juni 2019 00:01 | **Matchar inte:** Den första träffen på sida B matchar inte eftersom den står i konflikt med begränsningen som kräver den efter två veckor. |

### Använda operatorn Inom

* [!UICONTROL Within] Med kan du spåra efter år, månad, dag, timme och minut för att matcha besöken.
* [!UICONTROL Within] kan bara användas på en [!UICONTROL Hit] eftersom det är den enda nivån för vilken en sådan fin granularitet har definierats.

>[!TIP]
>
>I en&quot;inom&quot;-sats mellan THEN-programsatser kan du lägga till, till exempel,&quot;inom 1 nyckelordsinstans för sökning&quot;,&quot;inom 1 instans av eVar 47&quot;. Detta begränsar segmentet till en instans av en dimension.

**Exempel**: Besökare som besökt sida A och sedan besökt sida B inom fem minuter.

![](assets/time_between_within_operator.png)

**Skapa segmentet**: Det här segmentet skapas genom att du lägger till en [!UICONTROL Visitor] behållare och sedan dra med två [!UICONTROL Hit] behållare. Du kan sedan ange [!UICONTROL THEN] och öppna [!UICONTROL AFTER] operatorlistruta och ange intervall: träffar, sidvisningar, besök, minuter, timmar, dagar, veckor, månader, kvartal eller år.

![](assets/within_operator.png)

**Matchar**

Matchningar måste ske inom tidsgränsen. Om en besökare träffar sida A inträffar klockan 00:01 för uttrycket kommer nästa träff på sida B att matcha så länge som det kommer på eller före 00:06 (fem minuter senare, inklusive samma minut). Träffar inom samma minut kommer också att matcha.

### Operatorerna Inom och efter

Använd [!UICONTROL Within] och [!UICONTROL After] för att ge en högsta och lägsta slutpunkt i båda ändar av ett segment.

**Exempel**: Besökare som besökte sida A besökte sedan sida B efter två veckor, men inom en månad.

![](assets/time_between_using_both_operators.png)

**Skapa segmentet**: Skapa segmentet genom att sekvensera två [!UICONTROL Hit] behållare i en [!UICONTROL Visitor] behållare. Ange sedan [!UICONTROL After] och [!UICONTROL Within] operatorer.

![](assets/within_after_together.png)

**Matchar**

Alla besökare som träffar sida A den 1 juni 2019 återvänder efter den 15 juni 2019 kl. 00:01, men *före* 1 juli 2019 ingår i segmentet. Jämför med [Tid mellan undantag](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

The [!UICONTROL After] och [!UICONTROL Within] -operatorer kan användas tillsammans för att definiera ett sekventiellt segment.

![](assets/time_between_within_after.png)

I det här exemplet avbildas ett andra besök för att gå till sida B efter två veckor, men inom en månad.
