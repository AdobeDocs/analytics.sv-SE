---
description: Läs om de olika segmenteringsbehållarna och hur du använder dem
keywords: segmentering;segment
title: Segmentbehållare
feature: Segmentation
exl-id: f30d525b-32b7-47d5-b92d-24bf86d8a471
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '3548'
ht-degree: 1%

---


# Segmentbehållare

Ett segment ställer in villkor för att filtrera en besökare baserat på besökarens attribut eller interaktioner med platsen. Om du vill ange villkor i ett segment anger du regler för att filtrera besökare baserat på besökarens egenskaper och/eller navigeringsegenskaper. Om du vill dela upp besöksdata ytterligare kan du filtrera baserat på specifika besök och/eller sidvisningsträffar för varje besökare. Segmentbyggaren har en enkel arkitektur för att skapa dessa underuppsättningar och tillämpa regler som kapslade, hierarkiska besökar-, besöks- eller träbehållare.

Behållararkitekturen som används i [segmentbyggaren](/help/components/segmentation/segmentation-workflow/seg-build.md) definierar:

- ![Användare](/help/assets/icons/User.svg) **[!UICONTROL Visitor]** som den yttersta behållaren, som innehåller övergripande data som är specifika för besökaren vid besök och sidvisningar.
- ![Besök](/help/assets/icons/Visit.svg) en kapslad **[!UICONTROL Visit]** behållare där du kan ange regler för att dela upp besökarens data baserat på besök, och
- ![WebPage](/help/assets/icons/WebPage.svg) är en kapslad **[!UICONTROL Hit]** behållare som gör att du kan dela upp besökarinformation baserat på enskilda sidvyer.

Med varje behållare kan du rapportera över en besökares historik, interaktioner uppdelade efter besök eller dela upp individuella träffar.

<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>
</table>

<!--![](assets/sequential_segmentation_container_hierarchy.png)-->


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentbehållare](https://video.tv.adobe.com/v/3429102?quality=12&learn=on&captions=swe){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Besökarbehållare

Besökarbehållaren innehåller alla besök och sidvisningar för besökare inom en viss tidsperiod. Ett segment på besökarnivå returnerar den sida som uppfyller villkoret plus alla andra sidor som visas av besökaren (och som bara begränsas av definierade datumintervall). Rapporterna som genereras på besökarbehållarnivå är den mest definierade behållaren och returnerar sidvisningar för alla besök. Du kan generera en flerbesöksanalys. Det innebär att besökarbehållaren är den som kan ändras mest baserat på definierade datumintervall.

Besökarbehållare kan innehålla värden som baseras på besökarens övergripande historik:

- Dagar före första köpet
- Ursprunglig startsida
- Ursprungliga referensdomäner

## Besök container

Med besöksbehållaren kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss webbsession. Ett segment på besöksnivå returnerar den sida som uppfyller villkoret plus alla andra sidor som visas som en del av besökssessionen (och som endast begränsas av definierade datumintervall). Behållaren Visit är den vanligaste behållaren eftersom den fångar upp beteenden för hela besökssessionen när regeln har uppfyllts. Med besöksbehållaren kan du definiera vilka besök du vill inkludera eller exkludera när du skapar och använder ett segment. Det kan hjälpa er att besvara frågan om hur många besökare som har sett nyhetsavsnittet och sportavsnittet vid samma besök? Eller sidor som härrör från en lyckad konvertering till en försäljning?

Besöksbehållarna innehåller värden som baseras på förekomsten per besök:

- Besök nummer
- Inmatningssida
- Returfrekvens
- Deltagandemått
- Linjärt allokerade mätvärden

## Träffbehållare

Träffbehållaren definierar vilka sidträffar du vill ta med eller utesluta från ett segment. Träff-behållaren är den mest smala av de tillgängliga behållarna så att du kan identifiera specifika klick och sidvy där ett villkor är uppfyllt. Du kan visa en enskild spårningskod eller isolera beteenden i ett visst avsnitt på platsen. Du kanske också vill hitta ett specifikt värde när en åtgärd inträffar, till exempel marknadsföringskanalen när en beställning har gjorts.

Träffbehållare innehåller värden som är baserade på en sidindelning:

- Produkter
- Visa utkast
- List eVars
- Merchandising eVars (i samband med händelser)

  >[!NOTE]
  >
  >Om du använder den här behållaren på ett värde som kvarstår, t.ex. en evar, hämtas den i varje träff där värdet kvarstår. Om det finns en spårningskod som slutar gälla efter en vecka, kan det värdet bli bestående för flera besök.

## Behållare för logikgrupp

Med logikgruppsbehållaren kan du tillhandahålla en separat behållare inom segmentreglerna för att filtrera enheter som inte är baserade på hierarkin. Du kanske vill skapa en behållare som är kapslad i segmentet och som filtreras baserat på Visitor. Den här typen av logik kräver att du bryter hierarkin (eftersom du redan har använt en besöksbehållare på den översta nivån) för att filtrera enbart efter valda besökare. Mer information finns i [Exempel på logikgrupper](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

## Kapslade behållare {#nest-containers}

När du skapar segmentbehållare i andra behållare skapar du i princip ett segment i ett segment. Följande logik används med kapslade behållare:

1. Avgör vilka data som ska inkluderas med den yttersta behållaren. Alla data som inte matchar den här yttre regeln tas bort i den segmenterade rapporten.
1. Använd den kapslade regeln på återstående data. Den kapslade regeln gäller INTE för träffar som den första regeln genererar.
1. Upprepa tills alla kapslade behållarregler har beräknats. Resterande data inkluderas sedan i den resulterande rapporten.

>[!NOTE]
>
>När du kapslar in ett segment i ett segment (du t.ex. drar ett segment från panelen Komponenter till segmentdefinitionen) skapas en behållare med en kopia (inte en referens) av segmentlinjen som dras.

Du kan använda kapsling mellan behållare och mellan regler i en behållare. Det här är vad du kan kapsla i varje behållare:

| Behållarnamn | Vad du kan kapsla inuti |
|---|---|
| Träff | Endast händelser |
| Besök | Träffbehållare, händelser |
| Besökare | Besök container, Hit container, Events |
| Logikgrupp | Besökarbehållare, Besöksbehållare, Träff-behållare |

### Inkludera flera behållare i en enda definition

Om du inkluderar flera segment i ett nytt sammansatt segment kan du förfina data ännu mer. Om du drar ihop två befintliga segment fungerar det som en&quot;OR&quot;-sats när du filtrerar besökare. Alla behållare på arbetsytan granskas mot alla data, och alla data som matchar någon av behållarna inkluderas i rapporteringen.

Du kan till exempel dra en besöksbehållare där Land = USA med en besöksbehållare där Order = True,

```
Country = United States + Order = True
```

skapar ett segment som beter sig i den här ordningen:

1. Det här segmentet skulle först granska alla era data och identifiera alla besökare i USA.
2. Segmentet skulle då granska alla era data igen och söka efter om besökarna gjort en beställning.
3. Båda datauppsättningarna tillämpas sedan på rapporten.

## Behållare för sekventiella segment {#containers-sequential}

Sekventiell segmentering använder samma grundläggande behållare, inklusive [!UICONTROL Visitors], [!UICONTROL Visits] och [!UICONTROL Hits] (inklusive sidvyer eller andra dimensioner) kapslade hierarkiskt.

<table style="table-layout:fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>
</table>

<!--![](assets/nesting_container.png)-->

[!UICONTROL Visitors] utgör behållaren i den högsta ordningen i sekventiell segmentering, med [!UICONTROL Visits] inuti behållaren [!UICONTROL Visitors] och [!UICONTROL Hits] inuti behållarna [!UICONTROL Visitors] eller [!UICONTROL Visits]. Den här [behållarhierarkin](/help/components/segmentation/seg-overview.md#section_7FDF47B3C6A94C38AE40D3559AFFAF70) måste underhållas för att kunna skapa välordnade sekventiella segment.

**För att skapa sekventiella segment** kapslas behållare och sekventiell logik kopplas med operatorn [!UICONTROL THEN] som kräver att varje behållare är `true` baserat på besökarens sekvens.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">SEDAN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>
</table>

<!--![](assets/sequential_segmentation_nesting_3.png)-->

Det enda undantaget till den här behållarhierarkin är när [logikgruppsbehållaren](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md) används. Med behållaren [!UICONTROL Logic Group] kan du kapsla in en träff i en behållare utan ordning för att hämta händelser och dimensioner, men utanför en sekventiell ordning.

<table style="table-layout:fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Besökare</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">SEDAN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Group_18_N.svg"/> Grupp</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> Träffar</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Besök</td>
</tr>

</table>

<!--![](assets/logic_group_hierarchy.png)-->

## Rapporter baserade på behållardata {#reports}

Med behållare kan du filtrera olika data på olika sätt baserat på rapportvärden när du delar upp segment och tillämpar dem på rapporter.

Data som samlas in på varje nivå i hierarkin Besök > Träff-behållare påverkar hur du skapar dina segment. Om du använder samma segment som används för samma rapport med samma datauppsättning får du olika värden baserat på den behållare som du genererar rapporten från. Faktorer som behållarrapporteringsnivå och värdenas beständighet över träffar kan medföra betydande förändringar i rapportens noggrannhet.

### Grunderna för behållardata {#container-data}

Besökaren som visas nedan besökte till exempel en plats på det första besöket, landade på hemsidan och besökte sedan ytterligare tre sidor och bytte besök till en försäljning. Vid ett separat besök landade besökaren den här gången via produktsidan, sedan till hemsidan, tillbaka till produktsidan och stängde sedan sessionen efter att ha tittat på Winter Hats. Olika värden visas i rapporten baserat på de data som samlats in för varje behållare för segmentet.

Segmentet `Pages equals Winter Coat` nedan används för **sidrapporten**.


Baserat på den valda behållaren visar rapporten olika resultat för följande besök och sidvisningar av en besökare.

<table style="table-layout:auto; border: 0;">

<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;" colspan="4"><b>Besök 1</b></td>
</tr>
<tr>
<tr>
<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/>
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Startsida</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinter</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>Köp 100 dollar</td>
</tr>
<tr>
<td colspan="5">
</tr>
<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;"colspan="4"><b>Besök 2</b></td>
</tr>
<tr>
<tr style="border: 0;">

<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/>
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vintern - starter</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>Vinter-hattar</td>

</table>


<!--![](assets/container_overview.png)-->

### Rapportering från träffbehållaren

När det här villkoret finns i en Träff-behållare listas endast sidor där *Sida = Vintern* är true. Eftersom bara en sida matchar det här villkoret i en behållare för endast en sida, visas endast sidan Vinter-slag.

| Sida | Sidvisningar |
|---|--:|
| Vinter | 1 |

<!--![](assets/container_overview_PV.png)-->

Om du rapporterar från träff-behållaren kan du se hur rapporter från olika behållare påverkar de totala rapportvärdena. När du tittar på segmentrapporten ser du att sidvyerna är ungefär lika många som besöken (cirka 2 000 besökare såg dubblettsidor vid ett besök, vilket ökar det totala antalet sidvisningar). Och unika besökare är ungefär lika många som antalet besök (cirka 2 000 unika besökare besöktes mer än en gång).

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **69,252** av 351,292 <br/>**67,554** av 165,175 <br/>**63,541** av 113,169 | **19%**<br/>**40%**<br/>**56%** |


<!--![](assets/container_report_PV.png)-->

>[!IMPORTANT]
>
>Oavsett hur du visar data (från Träff-, Visit- eller Visitor-behållare) har de alla samma antal besökare, 63 541, i det här exemplet. Oberoende av hur du skapar rapporten förblir det inledande besökarvillkoret (besökare som visade sidan för vintertäckta) oförändrat. Det är den delmängd av data som du rapporterar från på olika nivåer.

### Rapportering från besöksbehållaren

Om samma villkor gäller för en besöksbehållare listas alla sidor i besöket där *Sida är lika med Vinter-slag* är sant. Den filtrerar sidan Vinter Coats, men hämtar även alla andra sidor vid besöket där villkoret är sant. Eftersom besökaren även besökte webbplatserna Hem, Produkt och Inköp vid besöket listas dessa ytterligare sidor i rapporten när de rapporteras med data om besöksbehållaren.

| Sida | Sidvisningar |
|---|--:|
| Startsida | 1 |
| Produkt | 1 |
| Vinter | 1 |
| Inköp | 1 |

<!--![](assets/container_overview_visit.png)-->

Genom att visa segmentvärden från besöksbehållaren ser du att antalet sidvisningar har ökat avsevärt. Ökningen beror på att rapporter från besöksbehållaren identifierar alla sidor som uppfyller villkoren, plus alla andra sidor som visas i besöket (med alla sidvyer tagna i varje besöksbehållare).

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **226,193** av 351,292 <br/>**67,554** av 165,175 <br/>**63,541** av 113,169 | **64%**<br/>**40%**<br/>**56%** |

<!--![](assets/container_report_Visit.png)-->

### Rapportering från besökarbehållaren

Om det här villkoret är i en besökarbehållare listas alla sidor som visas av en besökare där *Sida är lika med Vinter-slag* är sant. Det här villkoret innebär att om en besökare visar sidan Vinter Coats, listas alla sidor i besökarbehållaren (inklusive sidvyer i andra besök). Därför visas sidor som inte matchar villkoret också i rapporten eftersom besökaren visade dem vid en tidigare tidpunkt. Alla sidor i besökarbehållaren listas i rapporten, även om de förekommer tidigare och inte uppfyller villkoren specifikt.

| Besök 1<br/>sida | <br/>Sidvyer |
|---|--:|
| Startsida | 1 |
| Vinterkläder | 1 |
| Vinter | 1 |
| Inköp | 1 |

| Besök sida 2<br/> | <br/>Sidvyer |
|---|--:|
| Vinterkläder | 2 |
| Vintern - starter | 1 |
| Vinter-hattar | 1 |

| Besök 1 + Besök 2<br/>Sidan | <br/>Sidvyer |
|---|--:|
| Vinterkläder | 3 |
| Startsida | 1 |
| Vinter | 1 |
| Inköp | 1 |
| Vintern - starter | 1 |
| Vinter-hattar | 1 |

<!--![](assets/container_overview_visitors.png)-->

Om du visar segment från besökarbehållaren ser du att sidvyerna och besöken har ökat. Ökningen beror på att om besökaren bara besökt sidan Vinter Coats en gång (vilket gör villkoret sant) så kommer alla andra sidvisningar och alla andra besök som besökaren har tagit.

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **240,094** av 351,292 <br/>**83,823** av 165,175 <br/>**63,541** av 113,169 | **68%**<br/>**50%**<br/>**56%** |

<!--![](assets/container_report_Visitor.png)-->

Sammanfattningsvis är en förståelse för hur segmentering fungerar på olika datauppdelningar avgörande för att kunna tolka de data som returneras.

## Rapportering baserad på behållaren {#reporting}

Varje uppdelning av segmentdata har ett omfång som de tillämpas på. De flesta uppdelningar baseras på *sidvyer*, men många värdefulla segment baseras på behållaren *Besök* och i mindre utsträckning på behållaren *Besök* . Det är viktigt att förstå hur du rapporterar baserat på omfattningen av din behållare.

Med segmentexemplet `Page equals Winter Coats` nedan visas exempel på resultatet av det här segmentet utifrån hur behållardata används och hur omfattningen av data matchar segmenttypen.

### Segmentbehållare baserad på matchande segmentregel

Om segmentbehållaren används mot ett naturligt dataområde, förväntas resultatet när radobjekten matchar segmentregeln.

- **Träffbehållaren där sidan är lika med &quot;Vinter-katt&quot;**: Om du visar en *sida*-rapport med det här segmentet returneras bara de värden som är lika med &quot;Vinter-katt&quot;. Alla andra sidor undantas från rapporteringen.
- **Besöksbehållare där startsidan är lika med &quot;Vinter-kläder&quot;**: Om du visar en *anmälningssida*-rapport med det här segmentet returneras bara det andra besöket eftersom startsidan matchar segmentregeln.
- **Besöksbehållare där besöksnumret är lika med 1**: Visa alla sidvyer från det första besöket ingår i rapporten eftersom den matchar segmentregeln.

### Sidvyer på behållarnivå för besök

Många segmentregler identifierar sidvisningar per besök. När den här identifieringen inträffar tillämpas hela besökarbehållaren om endast en träff matchar regeln. Den här segmentrapporten är särskilt värdefull eftersom sidvisningar baserade på besök ger insikter baserade på sidvisningar per besök.

- **Besök en behållare där sidan är lika med sidan &quot;Vinter-katt&quot;**: I en sidrapport på behållarnivå för besökare visas alla sidvisningar av besök som innehåller en vy av sidan &quot;Vinter-kläder&quot;. Om en sida matchar segmentregeln inkluderas alla sidvyer som är kopplade till det besöket i rapporten.
- **Besök behållaren där sidan är lika med startsidan**: I en sidrapport med det här segmentet visas endast data från det första besöket, eftersom besökaren vid det andra besöket inte visade någon startsida.
- **Besökarbehållare där sidan är lika med &quot;Vinter-kläder&quot;**: I en sidrapport hämtar det här segmentet alla data från båda besöken, eftersom besökaren i båda besöken visade sidan &quot;Vinter-kläder&quot;.

### Segmentbehållare som identifierar träffar som är mindre än sidvyer

Om du använder segment med en mindre behållare än nedbrytningsområdet returneras oväntade data. Genom att använda en mindre uppdelning hämtas alla träffar från detta dataområde.

- **Träffbehållare där startsidan är lika med produktsidan**: Varje sida är associerad med besökets startsida, vilket gör den till en besöksbaserad uppdelning. När du använder det här segmentet hämtas inte bara startsidan för produktsidan, utan även alla träffar på besöket.
- **Träffbehållaren där List Var 1 innehåller ValueA**: Om flera värden har definierats i samma träff som listans var, inkluderas alla variabelvärden i segmentet. Det finns inget sätt att separera värden som förekommer i samma sidvy eftersom Träff-behållaren är den minsta segmentbehållaren för att bryta ned träffar.
- **Träffbehållare där sidan är lika med&quot;Inköp&quot;**: Om du använder sidvyer som mått visas bara sidan Inköp (som förväntat). Om du använder en Intäktsdeltagarrapport får alla sidor i det första besöket 100 dollar, eftersom deltagarstatistik är besöksbaserad.
- **Träffbehållare där sidan är lika med &quot;Vinter-katt&quot;**: Om du använder sidvyer som mätvärden visas endast Vinter-kägelsidan (som förväntat). Om du använder en Intäktsdeltagarrapport får inga sidor krediter eftersom denna dimension kräver en beständig dimension. Sidvyn som faktiskt gjorde köpet (sidan Inköp) inkluderas inte i Träff-behållaren, så ingen intäktsandel ges till någon artikel. Om du kör en rapport från besöksbehållaren skulle dock alla sidvisningar ingå i besöket och vinsten skulle fördelas ($100) över alla sidor som visas i sessionen.

## Beständig i alla behållare {#persistence}

Filtrering efter dimensioner som finns kvar på ett sidintervall, t.ex. en Campaign eVar eller en referensdimension, påverkar de data som samlas in på behållarnivå och måste förstås för att rapporteringen ska vara korrekt.

Segmentdata kan variera beroende på hur beständig en dimension eller en variabel som används på de valda sidorna är. Vissa dimensioner, till exempel siddimensionen, ger unika värden på sidnivå och filtreras baserat på data från Träff-behållaren. (Se exemplet [Rapporter baserade på behållardata](/help/components/segmentation/seg-overview.md)). Andra dimensioner, till exempel dimensionen Refererande domän, finns kvar på flera sidor för ett besök. Till exempel: `Referring Domain equals aol.com`. Vissa dimensioner eller tillämpade variabler, som Besök Varaktighet, spänner över en besökares hela historik.

<!--![](assets/RefDomain_aol.png)-->

I motsats till siddimensionen är referensdomänvärdet kopplat till varje sida i besöket. Besökaren nedan kommer till exempel till hemsidan från en refererad webbplats. Därför tilldelas alla sidor i besöket samma referensdomänvärde.

Segmentet `Referring Domain equals aol.com` nedan används för **sidrapporten**.

<table style="table-layout:fixed; border: 0;">

<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;" colspan="4"><b>Besök 1</b></td>
</tr>
<tr>
<tr>
<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/><br/>aol.com
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Startsida</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinter</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>Köp 100 dollar</td>
</tr>
<tr>
<td colspan="5">
</tr>
<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;"colspan="4"><b>Besök 2</b></td>
</tr>
<tr>
<tr style="border: 0;">

<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/><br/>weather.com
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vintern - starter</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>Vinterkläder</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>Vinter-hattar</td>

</table>

<!--![](assets/container_overview_persist.png)-->

Vid ett nytt besök hänvisas besökaren till från en annan plats. Därför tilldelas alla sidor i det nya besöket det nya referensdomänvärdet för varje sidvy.

### Rapportering från träffbehållaren

Eftersom alla sidvyer inom samma besök har tilldelats samma referensdomänvärde, rapporterar du på träff-behållarnivå där `Referring Domain equsls 'aol.com'` returnerar alla sidor i tabellen nedan.

| Refererande domän är lika med &#39;aol.com&#39; | Sidvisningar |
|----|---:|
| Startsida | 1 |
| Vinterkläder | 1 |
| Vinter | 1 |
| Inköp | 1 |

<!--![](assets/container_overview_persist_Visit.png)-->

Med data från Träff-behållaren visades drygt 92 000 sidvisningar i över 33 000 besök av drygt 32 000 besökare. I genomsnitt fanns det tre sidvisningar vid varje besök, och nästan alla besök gjordes av unika besökare.

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **98,234** av 351,165 <br/>**33,203** av 165,173 <br/>**32,269** av 113,110 | **27%**<br/>**20%**<br/>**28%** |

<!--![](assets/container_report_persist_PV.png)-->

### Rapportering från besöksbehållaren

Om samma villkor filtreras i besöksbehållaren för en sidrapport, kommer alla sidor i besöket där `Referring Domain equals 'aol.com'` är true. Eftersom värdet för den refererande domänen anges på besöksnivå är rapporterna på sidvynivå och besöksnivå desamma.

| Refererande domän är lika med &#39;aol.com&#39; | Sidvisningar |
|----|---:|
| Startsida | 1 |
| Vinterkläder | 1 |
| Vinter | 1 |
| Inköp | 1 |

<!--![](assets/container_overview_persist_Visit.png)-->

Eftersom alla sidor har samma referensdomänvärde baserat på besöket är rapporten från besöksbehållarnivån (nästan) densamma som rapporten från sidvisningsbehållaren. Det finns en liten förskjutning (98 234 mot 98 248) på grund av dataavvikelser.

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **98,248** av 351,165 <br/>**33,203** av 165,173 <br/>**32,269** av 113,110 | **27%**<br/>**20%**<br/>**28%** |

<!--![](assets/container_report_persist_Visit.png)-->

### Rapportering från besökarbehållaren

Från besökarbehållaren visar sidrapporten alla sidor som visas av en besökare där `Referring Domain equals 'aol.com'` är true. Om en besökare hade *&#39;aol.com&#39;* som hänvisande domän när som helst i historiken (inom den definierade tidsperioden) listas därför alla sidor i besökarbehållaren (inklusive sidvisningar i andra besök). Även sidor som inte matchar det primära villkoret listas i rapporten eftersom de här sidorna inkluderas i besökarbehållaren. Alla sidor i besökarbehållaren listas i rapporten, även om de förekommer tidigare och inte uppfyller villkoren specifikt.

I en referensdomänrapport är `Referring Domain equals 'aol.com'` true i fyra sidvyer, men `Referring Domain equals "weather.com"` är true i de andra sidorna besökaren träffar. I besökarbehållaren visas en lista med besökare där aol.com är true. Men det ger även dig sidor där den refererande domänen är&quot;wall.com&quot;, inte värdet som matchade din ursprungliga begäran i segmentet.

| Besök 1<br/>referensdomänen är lika med &#39;aol.com&#39; | <br/>Sidvyer |
|----|---:|
| Startsida | 1 |
| Vinterkläder | 1 |
| Vinter | 1 |
| Inköp | 1 |

| Besök 2<br/>Referensdomän = &#39;west.com&#39; | <br/>Sidvyer |
|----|---:|
| Vinterkläder | 2 |
| Vinter | 1 |
| Inköp | 1 |

| Besökarbehållare<br/>Referensdomän är lika med aol.com | Sidvisningar |
|----|---:|
| Vinter-kläder<br/>refererande domän: &#39;aol.com&#39; | 1 |
| Vinter-kläder<br/>refererande domän: &#39;west.com&#39; | 1 |
| Hem <br/>som refererar till domän: &#39;aol.com&#39; | 1 |
| Vinter-katt <br/>refererande domän: &#39;aol.com&#39; | 1 |
| Inköp<br/>Referensdomän: &#39;aol.com&#39; | 1 |
| Vinter-starter<br/>Referensdomän: &#39;west.com&#39; | 1 |
| Vinter-hattar<br/>refererande domän: &#39;west.com&#39; | 1 |


<!--![](assets/container_overview_persist_Visitor.png)-->

När du visar data från besökarbehållaren, observera att sidvyerna har ökat avsevärt (från 98 248 till 112, 925). Ökningen beror på att alla sidvyer som besökaren har sparat (inklusive de sidor där andra referensdomänvärden har sparats på behållarnivån för besökaren) har listats. Och besökarens ytterligare besök, som ökade antalet besök från 33 203 till 43 448.

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | Mått | # | % |
|---|---|--:|--:|
| | Sidvyer:<br/>Vyer:<br/>Unika besökare: | **112,925** av 351,165 <br/>**43,448** av 165,173 <br/>**32,269** av 113,110 | **32%**<br/>**26%**<br/>**28%** |

<!--![](assets/container_report_persist_Visitor.png)-->

## Sammanfattning

- Besökarbehållaren returnerar alla sidor som visas av en besökare där minst en sida uppfyller villkoren. Om en sida bara visas på besök 1 dag 1, inkluderas alla sidor som besökaren visar vid flera besök i data.
- Besöksbehållaren returnerar alla sidor som visas vid ett besök, för vilka minst en sida uppfyller villkoren. Om en sida bara visas på besök 1 dag 1 inkluderas alla sidor som visas under hela besöket i informationen.
- Var noga med att basera villkoret som du använder för segmentering på en eVar-variabel eller någon annan typ av beständig variabel. Du kan till exempel använda villkoret&quot;där kampanjen innehåller e-post&quot; och det upphör att gälla efter sju dagar. Så om kampanjen sätts in vid det första besöket kvarstår den i ytterligare sju dagar. Varje besök ingår även om kampanjen bara var planerad vid det första besöket. De övriga besöken ingår också (så länge de ligger inom rapportens datumintervall). Om du vill ta bort beständiga värden från att inkluderas använder du antingen händelsen &quot;instance of&quot; eller en motsvarande Prop-variabel, om en sådan finns.
