---
description: Sekventiella segment skapas med operatorn THEN i stället för AND eller OR. DÄREFTER betyder det att ett segmentvillkor är uppfyllt, följt av ett annat. Som standard identifierar ett sekventiellt segment alla matchande data och visar filtret Inkludera alla. Sekventiella segment kan filtreras ytterligare till en delmängd av matchande träffar med alternativen Endast före sekvens och Endast efter sekvens.
title: Skapa sekventiella segment
feature: Segmentation
exl-id: 2ac4e6db-3111-45e5-bedf-7d9b7b1ae352
source-git-commit: 564b5fd305f1c8c4e16a92d3b2094ba73ba91c4c
workflow-type: tm+mt
source-wordcount: '3762'
ht-degree: 1%

---

# Skapa sekventiella segment

Sekventiella segment skapas med operatorn THEN i stället för AND eller OR. DÄREFTER betyder det att ett segmentvillkor är uppfyllt, följt av ett annat. Som standard identifierar ett sekventiellt segment alla matchande data och visar filtret Inkludera alla. Sekventiella segment kan filtreras ytterligare till en delmängd av matchande träffar med alternativen Endast före sekvens och Endast efter sekvens.

![](assets/before-after-sequence.png)

Dessutom kan du begränsa sekventiella segment till en viss tidslängd, granularitet och antal mellan kontrollpunkter med operatorerna [Efter och Inom](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Här är en video om sekventiell segmentering:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Inkludera alla {#section_75ADDD5D41F04800A09E592BB2940B35}

När du skapar ett segment där Inkludera alla är angivet identifierar segmentet banor som matchar det angivna mönstret som helhet. Detta är ett exempel på ett grundläggande sekvenssegment som söker efter en träff (sida A) följt av en annan (sida B) som besökts av samma besökare. Segmentet är inställt på Inkludera alla.

![](/help/admin/admin/assets/filter.png)
![ 70a875e2-0ef9-4459-8648-77c60081d64d](assets/terrible-link-1.png)

| Om resultatet.. | Sekvens |
|--- |--- |
| Matchar | A sedan B<br>A sedan (vid ett annat besök) B<br>A sedan D och sedan B |
| Matchar inte | B och A |

## Endast före sekvens och Endast efter sekvens {#section_736E255C8CFF43C2A2CAAA6D312ED574}

Alternativen **[!UICONTROL Only Before Sequence]** och **[!UICONTROL Only After Sequence]** filtrerar segmentet till en delmängd med data före eller efter den angivna sekvensen.

* **Endast före sekvens**: Inkluderar alla träffar före en sekvens + den första träffen i själva sekvensen (se exempel 1, 3). Om en sekvens visas flera gånger i en bana innehåller&quot;Endast före sekvens&quot; den första träffen av den sista sekvensen i sekvensen och alla tidigare träffar (se exempel 2).
* **Endast efter sekvens**: Inkluderar alla träffar efter en sekvens + den sista träffen i själva sekvensen (se exempel 1, 3). Om en sekvens visas flera gånger i en bana innehåller&quot;Endast efter&quot; den senaste träffen av den första sekvensen och alla efterföljande träffar (se exempel 2).

Ta till exempel en sekvens av B -> D. De tre filtren identifierar träffar på följande sätt:

**Exempel 1: B och D visas en gång**

| Exempel | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Inkludera alla | A | B | C | D | E | F |
| Endast före sekvens | A | B |  |  |  |  |
| Endast efter sekvens |  |  |  | D | E | F |

**Exempel 2: B visas sedan D flera gånger**

| Exempel | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Inkludera alla | A | B | C | D | B | C | D | E |
| Endast före sekvens | A | B | C | D | B |  |  |  |
| Endast efter sekvens |  |  |  | D | B | C | D | E |

Låt oss även sätta ihop det här konceptet med djupdimensionen.

**Exempel 3: Träffdjup 3 och sedan 5**

![](assets/hit-depth.png)

## Begränsningar för Dimension {#section_EAFD755F8E674F32BCE9B642F7F909DB}

I en&quot;inom&quot;-sats mellan THEN-programsatser kan du lägga till, till exempel,&quot;inom 1 nyckelordsinstans för sökning&quot;,&quot;inom 1 eVar 47-instans&quot;. Detta begränsar segmentet till en instans av en dimension.

Om du ställer in en Within Dimension-sats mellan regler kan ett segment begränsa data till sekvenser där den satsen uppfylls. Se exemplet nedan, där begränsningen är inställd på &quot;Inom 1 sida&quot;:

![](assets/sequence-filter4.png)

| Om resultatet.. | Sekvens |
|--- |--- |
| Matchar | A och sedan B |
| Matchar inte | A then C then B (därför att B inte var inom 1 sida av A)<br>**Obs!** Om dimensionsbegränsningen är borttagen kommer både A och B och A och C och B att matcha. |

## Enkel sidvisningssekvens

Identifiera besökare som visade en sida och sedan visade en annan sida. Data på träffnivå filtrerar den här sekvensen oavsett tidigare, tidigare eller tillfälliga besökssessioner eller tidpunkten eller antalet sidvisningar som inträffar mellan.

**Exempel**: Besökaren visade sida A och visade sedan sida B i samma eller ett annat besök.

**Användningsexempel**

Här följer några exempel på hur segmentet kan användas.

1. Besökarna på en sportsajt kan se landningssidan för fotboll och sedan se landningssidan för basketboll i ordningsföljd, men inte nödvändigtvis på samma besök. Detta får en kampanj för att göra basketinnehåll till fotbollstittare under fotbollssäsongen.
1. Bilhandlarna ser en relation mellan dem som landar på kundlojalitetssidan och sedan går till videon när som helst under besöket eller vid ett annat besök.

**Skapa det här segmentet**

Du kapslar in två sidlinjaler i en [!UICONTROL Visitor]-behållare på den översta nivån och sekventierar sidträffarna med operatorn [!UICONTROL THEN] .

![](assets/segment_sequential_1.png)

## Besökssekvens mellan besök

Identifiera de besökare som föll ned från en kampanj men sedan återvände till sekvensen av sidvisningar i en annan session.

**Exempel**: Besökaren visade sida A vid ett besök och visade sedan sida B vid ett annat besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökarna på Sports-sidan på en nyhetsplats går sedan igenom Sports-sidan i en annan session.
* En klädhandlare ser en relation mellan besökare som landar på en landningssida under en session och sedan går direkt till utcheckningssidan under en annan session.

**Skapa det här segmentet**

I det här exemplet kapslas två **[!UICONTROL Visit]**-behållare in den översta **[!UICONTROL Visitor]**-behållaren och segmentet sekventieras med operatorn [!UICONTROL THEN] .

![](assets/visitor_seq_across_visits.png)

## Sekvens på blandnivå

Identifiera besökare som tittar på två sidor över ett obestämt antal besök, men sedan visa en tredje sida vid ett separat besök.

**Exempel**: Besökarna besöker sida A och sedan sida B i ett eller flera besök, följt av ett besök på sida C i ett separat besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökarna besöker först en nyhetssajt och ser sedan sportsidan i samma besök. På ett annat besök besöker besökaren vädersidan.
* Återförsäljaren definierar besökare som går in på huvudsidan och sedan går till sidan Mitt konto. De besöker även sidan Visa kundvagn.

**Skapa det här segmentet**

1. Släpp två siddimensioner från de vänstra rutorna i en [!UICONTROL Visitor]-behållare på den översta nivån.
1. Lägg till operatorn THEN mellan dem.
1. Klicka på **[!UICONTROL Options]** > **[!UICONTROL Add container]** och lägg till en [!UICONTROL Visit]-behållare under nivån [!UICONTROL Visitor] och sekvenserad med operatorn [!UICONTROL THEN].

![](assets/mixed_level_checkpoints.png)

## Sammanställningsbehållare

Om du lägger till flera [!UICONTROL Hit]-behållare i en [!UICONTROL Visitor] -behållare kan du använda lämpliga operatorer mellan samma typ av behållare och använda regler och dimensioner som Sida och Besöksnummer för att definiera sidvyn och tillhandahålla en sekvensdimension i [!UICONTROL Hit]-behållaren. Genom att använda logik på träff-nivå kan du begränsa och kombinera matchningar på samma nivå av träffar i [!UICONTROL Visitor]-behållaren för att skapa en mängd olika segmenttyper.

**Exempel**: Besökarna besökte sida A efter den första träffen i sidvysekvensen (sida D i exemplet) och besökte sedan antingen sida B eller sida C utan hänsyn till antalet besök.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Identifiera besökare som går till huvudlandningssidan på ett besök, och se sedan sidan med kläder för män på ett annat besök, och titta sedan på antingen Womans eller Children&#39;s landningssida vid ett annat besök.
* Ett e-zine fångar de besökare som går till hemsidan vid ett besök, på en annan sajt och på en annan besökssida.

**Skapa det här segmentet**

1. Välj behållaren [!UICONTROL Visitor] som behållare på den översta nivån.
1. Lägg till två behållare på [!UICONTROL Hit]-nivå - en dimension med en lämplig numerisk dimension som förenas på samma [!UICONTROL Hit]-nivå av operatorn [!UICONTROL AND] och [!UICONTROL OR] .
1. Lägg till ytterligare en [!UICONTROL Hit]-behållare i behållaren [!UICONTROL Visit] och kapsla ytterligare två [!UICONTROL Hit]-behållare som är kopplade till en [!UICONTROL OR] - eller [!UICONTROL AND] -operator.

   Sekvens för dessa kapslade [!UICONTROL Hit]-behållare med operatorn [!UICONTROL THEN].

![](assets/aggregate_checkpoints2.png)

## &quot;Kapsling&quot; i sekventiella segment

Genom att placera kontrollpunkter på både [!UICONTROL Visit]- och [!UICONTROL Hit]-nivån kan du begränsa segmentets storlek så att det uppfyller kraven inom ett visst besök samt en viss träff.

**Exempel**: Besökaren besökte sida A och besökte sedan sida B vid samma besök. Vid ett nytt besök gick besökaren till sida C.

**Skapa det här segmentet**

1. Dra i två sidstorlekar under en [!UICONTROL Visit]-behållare på den översta nivån.
1. Markera båda reglerna flera gånger, klicka **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]** och ändra den till en [!UICONTROL Visit]-behållare.
1. Koppla dem till en [!UICONTROL THEN]-operator.
1. Skapa en Träff-behållare som en peer-dator till [!UICONTROL Visit]-behållaren och dra i en siddimension.
1. Koppla den kapslade sekvensen i [!UICONTROL Visit]-behållaren med [!UICONTROL Hit]-behållaren med en annan [!UICONTROL THEN]-operator.

![](assets/nesting_sequential_seg.png)

## Exkludera träffar

Segmentregler inkluderar alla data såvida du inte uttryckligen utesluter [!UICONTROL Visitor]-, [!UICONTROL Visit]- eller [!UICONTROL Hit]-data med regeln [!UICONTROL Exclude]. Det gör att ni kan avfärda vanliga data och skapa segment med mer fokus. Eller så kan du skapa segment som utesluter hittade grupper för att identifiera den återstående datauppsättningen, till exempel skapa en regel som innefattar framgångsrika besökare som lade order och sedan exkludera dem för att identifiera&quot;icke-köpare&quot;. I de flesta fall är det dock bättre att skapa regler som utesluter breda värden i stället för att använda regeln [!UICONTROL Exclude] för att ange specifika inkluderingsvärden som mål.

Exempel:

* **Uteslut sidor**. Använd en segmentregel om du vill ta bort en viss sida (till exempel *`Home Page`*) från en rapport, skapa en träff-regel där sidan är lika med&quot;Hemsida&quot; och exkludera den sedan. Den här regeln inkluderar automatiskt alla värden förutom hemsidan.
* **Uteslut refererande domäner**. Använd en regel som endast inkluderar refererande domäner från Google.com och exkluderar alla andra.
* **Identifiera icke-köpare**. Identifiera när order är större än noll och exkludera sedan [!UICONTROL Visitor].

Operatorn [!UICONTROL Exclude] kan användas för att identifiera en sekvens där specifika besök eller träffar inte utförs av besökaren. [!UICONTROL Exclude Checkpoints] kan också ingå i en [logikgrupp](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

### Uteslut mellan kontrollpunkter

Använd logik för att segmentera besökare där en kontrollpunkt inte uttryckligen förekommer mellan två andra kontrollpunkter.

**Exempel**: Besökare som besökt sida A och sedan besökt sida C - men som inte besökt sida B.

**Användningsexempel**

Här följer några exempel på hur den här typen av segment kan användas:

* Besökare på en livsstilssida och sedan på Theatre utan att gå till Arts-sidan.
* En bilhandlare ser en relation mellan dem som besöker landningssidan och sedan går direkt till kampanjen&quot;Inget intresse&quot; utan att gå till sidan&quot;Fordon&quot;.

**Skapa det här segmentet**

Skapa ett segment på samma sätt som för ett enkelt, blandat eller kapslat sekventiellt segment och ange sedan operatorn [!UICONTROL EXCLUDE] för behållarelementet. Exemplet nedan är ett sammanställningssegment där de tre [!UICONTROL Hit] behållarna dras till arbetsytan, operatorn [!UICONTROL THEN] som har tilldelats för att sammanfoga behållarlogiken, och sedan utelämnar behållaren för den mellersta sidvyn så att endast besökare som gick från sidan A till sidan C inkluderas i sekvensen.

![](assets/exclude_between_checkpoints.png)

### Uteslut i början av sekvensen

Om kontrollpunkten för uteslutning är i början av ett sekventiellt segment ser den till att en utesluten sidvy inte inträffade före den första icke-uteslutna träffen.

En restaurang vill till exempel se användare som tenderar att undvika huvudlandningssidan och gå direkt till sidan Beställ ut. Du kan visa dessa data genom att utesluta träffar på landningssidan och inkludera träffar på sidan Ordna ut i ett sekventiellt segment.

**Skapa det här segmentet**

Skapa två separata träff-behållare i en besöksbehållare på den översta nivån. Ange sedan operatorn [!UICONTROL EXCLUDE] för den första behållaren.

![](assets/exclude_beginning_sequence.png)

### Uteslut vid sekvensslut

Om den utelämnade kontrollpunkten finns i slutet av en sekvens ser det till att kontrollpunkten inte inträffade mellan den sista icke-utelämnade kontrollpunkten och slutet av besökarsekvensen.

En klädbutik vill till exempel se alla besökare som tittade på en produktsida men aldrig besökt sin kundvagn efteråt. Det här exemplet kan förenklas för en besökare som går till sida A och sedan aldrig kommer till sida B vid aktuella eller efterföljande besök.

**Skapa det här segmentet**

Skapa ett enkelt sekvenssegment genom att dra två [!UICONTROL Hit]-behållare till arbetsytan och koppla dem med operatorn [!UICONTROL THEN] . Tilldela sedan operatorn [!UICONTROL EXCLUDE] till den andra [!UICONTROL Hit]-behållaren i sekvensen.

![](assets/exclude_end_sequence.png)

## Behållare för logikgrupp

Behållare för logikgrupp krävs för att gruppera villkor i en enda kontrollpunkt för sekventiellt segment. Den speciella logikgruppsbehållaren är endast tillgänglig i sekventiell segmentering för att säkerställa att villkoren uppfylls efter en sekventiell kontrollpunkt och före efterföljande kontrollpunkter. Villkoren i Logic Group-kontrollpunkten kan uppfyllas i vilken ordning som helst. Icke-sekventiella behållare (träff, besök, besökare) kräver däremot inte att deras villkor uppfylls i den övergripande sekvensen, vilket ger ointuitiva resultat om de används med en THEN-operator.
Behållaren [!UICONTROL Logic Group] har utformats för att behandla *flera kontrollpunkter som en grupp*, *utan någon ordning* bland de grupperade kontrollpunkterna. Med andra ord, vi bryr oss inte om ordningen på kontrollpunkterna i den gruppen. Du kan till exempel inte kapsla en [!UICONTROL Visitor]-behållare i en [!UICONTROL Visitor]-behållare. I stället kan du kapsla en [!UICONTROL Logic Group]-behållare i en [!UICONTROL Visitor]-behållare med specifika kontrollpunkter på [!UICONTROL Visit]- och [!UICONTROL Hit]-nivå.

>[!NOTE]
>
>[!UICONTROL Logic Group] kan bara definieras i ett sekventiellt segment, vilket innebär att operatorn [!UICONTROL THEN] används i uttrycket.

| Behållarhierarki | Illustration | Definition |
|---|---|---|
| Standardbehållarhierarki | ![](assets/nesting_container.png) | I behållaren [!UICONTROL Visitor] kapslas behållarna [!UICONTROL Visit] och [!UICONTROL Hit] i sekvens för att extrahera segment baserat på träffar, antalet besök och besökaren. |
| Logikbehållarhierarki | ![](assets/logic_group_hierarchy.png) | Standardbehållarhierarkin krävs även utanför behållaren [!UICONTROL Logic Group]. Men i behållaren [!UICONTROL Logic Group] kräver kontrollpunkterna ingen etablerad ordning eller hierarki. Dessa kontrollpunkter måste bara uppfyllas av besökaren i valfri ordning. |

Logikgrupper kan verka skrämmande - här följer några tips om hur du använder dem:

**Logggrupp eller Träff/Besök behållare?**
Om du vill gruppera sekventiella kontrollpunkter är din&quot;behållare&quot; logikgrupp. Om dessa sekventiella kontrollpunkter måste finnas inom ett enda träffs- eller besöksomfång, krävs dock en träff- eller besöksbehållare. (En träff passar förstås inte för en grupp av sekventiella kontrollpunkter, när en träff inte kan kreditera mer än en kontrollpunkt).

**Förenklar logiska grupper skapandet av sekventiella segment?**
Ja, det kan de. Låt oss anta att du försöker identifiera det här besökarsegmentet: **Besökare som visade sida A och sedan visade sidorna i B, C och D**

Du kan skapa det här segmentet utan en logikgruppsbehållare, men det är komplicerat och mödosamt. Du måste ange varje sidsekvens som besökaren kan visa:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

En logikgruppsbehållare förenklar byggandet av det här segmentet avsevärt, vilket visas här:

![](assets/logic-grp-example.png)


### Skapa ett logikgruppssegment {#section_A5DDC96E72194668AA91BBD89E575D2E}

Precis som andra behållare kan [!UICONTROL Logic Group]-behållare byggas på flera sätt i [!UICONTROL Segment Builder]. Här är ett föredraget sätt att kapsla [!UICONTROL Logic Group] behållare:

1. Dra mått, händelser eller segment från de vänstra rutorna.
1. Ändra den övre behållaren till en [!UICONTROL Visitor]-behållare.
1. Ändra operatorn [!UICONTROL AND] eller [!UICONTROL OR] infogad som standard till operatorn THEN.
1. Markera [!UICONTROL Hit]-behållarna (Dimensionen, händelsen eller objektet) och klicka på **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**.
1. Klicka på behållarikonen och välj **[!UICONTROL Logic Group]**. ![](assets/logic_group_checkpoints.png)
1. Du kan nu ange [!UICONTROL Hit] i [!UICONTROL Logic Group]-behållaren utan hänsyn till hierarkin.

### Kontrollpunkter för logikgrupp i vilken ordning som helst

Om du använder [!UICONTROL Logic Group] kan du uppfylla villkoren i den gruppen som ligger utanför sekvensen. Detta gör att du kan skapa segment där en [!UICONTROL Visit]- eller [!UICONTROL Hit]-behållare inträffar oavsett den normala hierarkin.

**Exempel**: Besökare som besökt sida A och sedan besökt sida B och sida C i valfri ordning.

**Skapa det här segmentet**

Sida B och C är kapslade i en [!UICONTROL Logic Group]-behållare i den yttre [!UICONTROL Visitor]-behållaren. Behållaren [!UICONTROL Hit] för A följs sedan av behållaren [!UICONTROL Logic Group] med B och C som identifieras med operatorn [!UICONTROL AND]. Eftersom den finns i [!UICONTROL Logic Group] är sekvensen inte definierad och om du trycker på både sida B och C i någon ordning blir argumentet true.

![](assets/logic_group_any_order2.png)

**Ett annat exempel**: Besökare som besökt sida B eller sida C och sedan besökt sida A:

![](assets/logic_group_any_order3.png)

Segmentet måste matcha vid minst en av logikgruppens kontrollpunkter (B eller C). Logikgruppsvillkor kan även uppfyllas i samma träff eller över flera träffar. &#x200B;

### Logggruppsmatchning

Om du använder [!UICONTROL Logic Group] kan du uppfylla villkoren i den gruppen som ligger utanför sekvensen. I det här osorterade första matchningssegmentet identifieras reglerna [!UICONTROL Logic Group] först som antingen en sidvy av sida B eller sida C, och därefter som en nödvändig vy av sida A.

**Exempel**: Besökare som besökt antingen sida B eller sida C och sedan besökt sida A.

**Skapa det här segmentet**

Dimensionerna för sida B och C grupperas i en [!UICONTROL Logic Group]-behållare med operatorn [!UICONTROL OR] markerad, och sedan [!UICONTROL Hit]behållaren som identifierar en sidvy på sida A som värdet.

![](assets/logic_group_1st_match.png)

### Logikgrupp exkluderar OCH

Bygg segment med [!UICONTROL Logic Group] där flera sidvyer slås samman för att definiera vilka sidor som behöver mötas medan andra sidor specifikt missades. ****

**Exempel**: Besökaren besökte sida A, men besökte inte sida B eller C explicit, utan sidan D.

**Skapa det här segmentet**

Bygg segmentet genom att dra Dimensioner, händelser och färdiga segment från den vänstra panelen. Se [Skapa ett logiskt gruppsegment](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

När du har kapslat värdena i [!UICONTROL Logic Group] klickar du på knappen **[!UICONTROL Exclude]** i behållaren [!UICONTROL Logic Group].

![](assets/logic_exclude_and.png)

### Logikgrupp exkluderad ELLER

Bygg segment med [!UICONTROL Logic Group] där flera sidvyer slås samman för att definiera vilka sidor som behöver mötas medan andra sidor specifikt missades.

**Exempel**: Besökare som besökt sida A men inte besökt sida B eller sida C före sida A.

**Skapa det här segmentet**

De första B- och C-sidorna identifieras i en [!UICONTROL Logic Group]-behållare som är exkluderad och följs sedan av besökaren en träff till sida A.

Bygg segmentet genom att dra Dimensioner, händelser och färdiga segment från den vänstra panelen.

När du har kapslat värdena i [!UICONTROL Logic Group] klickar du på knappen **[!UICONTROL Exclude]** i behållaren [!UICONTROL Logic Group].

![](assets/logic_exclude_or.png)

## Bygg tidsbesparande och tidsbesparande segment

Använd operatorerna [!UICONTROL Within] och [!UICONTROL After] som är inbyggda i huvudet för varje behållare för att definiera tid, händelser och antal.

![](assets/then_within_operators.png)

Du kan begränsa matchningen till en angiven tidslängd genom att använda behållarna [!UICONTROL Within] och [!UICONTROL After] och ange en granularitet och ett antal. Operatorn [!UICONTROL Within] används för att ange en maxgräns för hur lång tid det tar mellan två kontrollpunkter. Operatorn [!UICONTROL After] används för att ange en minimigräns för hur lång tid det tar mellan två kontrollpunkter.

>[!NOTE]
>
>Det finns skillnader i utvärderingen mellan element med liknande namn, som **dag(ar)** eller **dag**. För tidsbaserade definitioner av Inom och efter använder du de alternativ som listas först i popup-fönstret:
>
>![bild](assets/terrible-link-2.png)
>
>Använd alternativen under undermenyn *Andra Dimensioner* för dimensionsbaserade definitioner för Inom och efter:
>
>![bild](assets/terrible-link-3.png)

### Efter och inom operatorer {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

Längden anges med en versal som representerar granulariteten följt av en siffra som representerar repetitionsantalet för granulariteten.

**[!UICONTROL Within]** innehåller slutpunkten (mindre än eller lika med).

**[!UICONTROL After]** innehåller inte slutpunkten (större än).

| Operatorer | Beskrivning |
|--- |--- |
| EFTER | Operatorn Efter används för att ange en minimigräns för hur lång tid det tar mellan två kontrollpunkter. När du anger After-värdena börjar tidsgränsen när segmentet används. Om till exempel operatorn Efter är inställd på en behållare för att identifiera besökare som besöker sida A men inte återvänder till sida B förrän efter en dag, börjar den dagen när besökaren lämnar sida A.  För att besökaren ska kunna inkluderas i segmentet måste minst 1440 minuter (en dag) visas efter att sidan A har lämnat sidan till sidan B. |
| INOM | Operatorn Inom används för att ange en maximal tidsgräns mellan två kontrollpunkter. Om till exempel operatorn Inom är inställd på en behållare för att identifiera besökare som besöker sida A och sedan återgår till sida B inom en dag, börjar den dagen när besökaren lämnar sida A. För att inkluderas i segmentet får besökaren högst en dag innan sidan B öppnas.   För att besökaren ska kunna delta i segmentet måste besöket på sida B äga rum inom högst 1440 minuter (en dag) efter att sidan A har lämnat sidan B. |
| EFTER/INOM | När du använder operatorerna Efter och Inom är det viktigt att du förstår att båda operatorerna börjar och slutar parallellt, inte sekventiellt.   Om du till exempel skapar ett segment med behållaren inställd på:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>uppfylls villkoren för att identifiera besökare i segmentet endast mellan 1 och 2 veckor. Båda villkoren tillämpas från och med den första sidträffen. |

### Använda operatorn Efter

* Med Tid efter kan du följa upp besök per år, månad, dag, timme och minut.
* Tid efter kan bara användas för en [!UICONTROL Hit]-behållare eftersom det är den enda nivån för vilken sådan fin granularitet har definierats.

**Exempel**: Besökare som besökt sida A besökte sida B först efter 2 veckor.***

![](assets/time_between_after_operator.png)

**Skapa segmentet**: Det här segmentet skapas genom att en [!UICONTROL Visitor]-behållare med två [!UICONTROL Hit]-behållare läggs till. Du kan sedan ange operatorn [!UICONTROL THEN], öppna listrutan [!UICONTROL AFTER] och ange antalet veckor.

![](assets/after_operator.png)

**Matchar**

Om en träff på sida A inträffar den 1 juni 2019, kl. 00:01, kommer följande träff på sida B att matchas så länge som det kommer före den 15 juni 2019 kl. 00:01 (14 dagar senare).

| Tryck på A | Träff B | Matchande |
|--- |--- |--- |
| **En** träff: 1 juni 2019 00:01 | **B** träff: 15 juni 2019 00:01 | **Matchar:** Tidsbegränsningen matchar eftersom den är efter 1 juni 2019 (två veckor). |
| **En** träff: 1 juni 2019 00:01 | **B** träffad: 8 juni 2019 00:01 B träffad: 15 juni 2019 00:01 | **Matchar inte:** Den första träffen på sida B matchar inte eftersom den står i konflikt med begränsningen som kräver den efter två veckor. |

### Använda operatorn Inom

* Med [!UICONTROL Within] kan du spåra efter år, månad, dag, timme och minut för att matcha besöken.
* [!UICONTROL Within] kan bara användas på en [!UICONTROL Hit]-behållare eftersom det är den enda nivån för vilken sådan fin granularitet har definierats.

>[!TIP]
>
>I en&quot;inom&quot;-sats mellan THEN-programsatser kan du lägga till, till exempel,&quot;inom 1 nyckelordsinstans för sökning&quot;,&quot;inom 1 eVar 47-instans&quot;. Detta begränsar segmentet till en instans av en dimension.

**Exempel**: Besökare som besökt sida A och sedan besökt sida B inom fem minuter.

![](assets/time_between_within_operator.png)

**Skapa segmentet**: Det här segmentet skapas genom att du lägger till en [!UICONTROL Visitor]-behållare och sedan drar med två [!UICONTROL Hit]-behållare. Du kan sedan ange operatorn [!UICONTROL THEN] och öppna listrutan för operatorn [!UICONTROL AFTER] och ange intervallet: träffar, sidvisningar, besök, minuter, timmar, dagar, veckor, månader, kvartal eller år.

![](assets/within_operator.png)

**Matchar**

Matchningar måste ske inom tidsgränsen. Om en besökare träffar sida A inträffar klockan 00:01 för uttrycket kommer nästa träff på sida B att matcha så länge som det kommer på eller före 00:06 (fem minuter senare, inklusive samma minut). Träffar inom samma minut kommer också att matcha.

### Operatorerna Inom och efter

Använd [!UICONTROL Within] och [!UICONTROL After] för att ange en högsta och lägsta slutpunkt i båda ändar av ett segment.

**Exempel**: Besökare som besökt sida A besökte sida B efter två veckor men inom en månad.

![](assets/time_between_using_both_operators.png)

**Skapa segmentet**: Skapa segmentet genom att sekvensera två [!UICONTROL Hit] -behållare i en [!UICONTROL Visitor] -behållare. Ange sedan operatorerna [!UICONTROL After] och [!UICONTROL Within].

![](assets/within_after_together.png)

**Matchar**

Alla besökare som träffar sida A den 1 juni 2019 återvänder efter den 15 juni 2019 00:01, men *före* 1 juli 2019 inkluderas i segmentet. Jämför med [Tid mellan undantag](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Operatorerna [!UICONTROL After] och [!UICONTROL Within] kan användas tillsammans för att definiera ett sekventiellt segment.

![](assets/time_between_within_after.png)

I det här exemplet avbildas ett andra besök för att gå till sida B efter två veckor, men inom en månad.
